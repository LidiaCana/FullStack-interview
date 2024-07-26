## Max consecutive numbers

write a function which accepts two parameters one array of integer and number, the function should return the maximum sum of consecutive "n" elements

Bonus: Avoid use nested for o(n^2)

## Solution

function maxSumArray(arr, num){
if(arr.length<num)return null;
let maxSum = arr[0];
let tempSum = maxSum;
for(let i = 1; i<num; i++){
maxSum += arr[i];
}
for(let j=num; j< arr.length; j++){
let firstToSum = arr[j-num];
let lastToSum = arr[j];
tempSum = maxSum-firstToSum+lastToSum;
if(tempSum>maxSum)maxSum=tempSum;
}
return maxSum;
}
