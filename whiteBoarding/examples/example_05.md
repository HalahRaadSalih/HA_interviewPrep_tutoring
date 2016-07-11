## Example 05

Problem

Given a non-negative integer num, repeatedly add all its digits until the result has only one digit.

For example:

Given num = 38, the process is like: 3 + 8 = 11, 1 + 1 = 2. Since 2 has only one digit, return it.

```
	// separate digits by converting to string first
	// and converting string to arry using split
    var digits = num.toString().split('');
    // initial summation of digits is zero
    var sum = 0;
    
    // if you have one digit, return the digit
    // as a number
    if(digits.length === 1){
    	return parseInt(digits[0]);
    }
    
    else{
    	// loop thru the digits
    	for(var i = 0; i < digits.length; i++){
    		//convert to number and add them
    		sum += parseInt(digits[i]);
     	}
     	// get the new sum and convert it to digits again
     	 return addDigits(sum);
     	
    }
    

```