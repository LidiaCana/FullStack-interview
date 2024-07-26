import { expect, test } from 'vitest'

import { asyncRetry } from './asyncRetry'

// This is just a safety mechanism to prevent the candidate from getting stuck in an
// infinite loop forcing them to restart the tests server
const infiniteLoopLimit = 20
const infiniteLoopMessage = 'You hit an infinite loop! 💀'

test('asyncRetry should return the result of the function if it succeeds', async () => {
const successResult = 'Success!'
const fn = async () => successResult
const limit = 5
const returnedResult = await asyncRetry(fn, limit);

expect(returnedResult).toBe(successResult)
})

test('asyncRetry should return the result of the function if it succeeds before retry limit is reached', async () => {
const testCases = [
{
successResult: 'Success!',
errorMessage: 'Test error',
succeedAfter: 2,
limit: 5,
},
{
successResult: '42!',
errorMessage: '42',
succeedAfter: 7,
limit: 12,
},
]

for (const { successResult, errorMessage, succeedAfter, limit } of testCases) {
let count = 0
const fn = async () => {
count++
if (count === succeedAfter) {
return successResult
}
if (count === infiniteLoopLimit) {
return infiniteLoopMessage
}
throw new Error(errorMessage)
}
const returnedResult = await asyncRetry(fn, limit)
expect(count).toBe(succeedAfter)
expect(returnedResult).toBe(successResult)
}
})

test('asyncRetry should retry the function n times before throwing an error', async () => {
const testCases = [
{
errorMessage: 'Test error',
limit: 5,
},
{
errorMessage: '42',
limit: 12,
},
]

for (const { errorMessage, limit } of testCases) {
let count = 0
const fn = async () => {
count++
if (count === infiniteLoopLimit) {
return infiniteLoopMessage
}
throw new Error(errorMessage)
}
await expect(asyncRetry(fn, limit)).rejects.toThrow(errorMessage)
expect(count).toBe(limit)
}
})

<!-- Solution -->

export const asyncRetry = async <T>(
fn: () => Promise<T>,
limit: number,
): Promise<T> => {
// Write your code here

let lastError: any;

for (let attempt = 1; attempt <= limit; attempt++) {
try {
const result = await fn();
return result; // If successful, return the result
} catch (error) {
lastError = error; // Capture the error

    }

}

throw lastError;

}
