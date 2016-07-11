## Example 07
### Problem
write a function that takes in an array of numbers and if the array has any zeros, the zeros are moved to the back of the array
####Example
-> [0,1,0,3,12]
<br>
output = [1,3,12,0,0]
### Solution

```
	var moveZeroes = function(nums) {
	var shiftedNumber;
    // loop thru Array
    for(var i = 0; i < nums.length; i++){
    // find zero
    	if(nums[i] === 0){
    		// shift array
    		shiftedNumber = nums.splice(i,1)[0];
    		// move shifted item to the back of the array
    		nums.push(shiftedNumber);
    	}
    }
    
    return nums;
    
};

moveZeroes([0, 1, 0, 3, 12]);
```