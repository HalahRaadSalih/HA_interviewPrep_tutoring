## Example 06

### Problem
Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

Example: 19 is a happy number

12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1

### Solutoin

```
	var isHappy = function(n) {
    // separate digits by converting to string first
	// and converting string to array using split
    var digits = n.toString().split('');
    // initial summation of digits is zero
    var sum = 0;
    // loop thru the digits
	for(var i = 0; i < digits.length; i++){
		//convert to number, sqaure it and add them
		sum += Math.pow(parseInt(digits[i]),2);
 	}
    
    if(sum === 4 || sum === 58 || sum === 37){
    	return false;
    }
    if(sum === 1){
    	return true
    }
    
    else{
    	return isHappy(sum);
    }

};

isHappy(2);```