## Multi-pointer Pattern

Write a function called sumZero which accept a sorted array of integer. The function should find the first pair where the sum is zero. return an array that includes both values or undefined if does not exist sum 0.

\*\* Avoid O(n^2) solutions
[-3,-1,0,1,2,4]

## Solutions

function sumZero(arr){
let indexLeft = 0;
let indexRight = arr.length -1

while(indexLeft< indexRight){
let sum = arr[indexLeft] + arr[indexRight];
if(sum===0) {return [arr[indexLeft] , arr[indexRight]]}
else if(sum>0){
indexRight--
}else{
indexLeft++
}
}
}
