## Example 03

### Problem

Given a positive integer num, write a function which returns True if num is a perfect square else False.

### Solution
- What is a perfect square? 25 is perfect square because 5 * 5 = 25. 8 is not a perfect sqaure because there is no number that you multiply it by itself that would return 8.

- Can I use math.sqrt? No you can't, that would be too easy. 
- Hmm, what if I loop from 1 till the input num and see if that number times itself equales the input num? Sounds perfectly legit. Let's give it a try. 

```
var isPerfectSqaure = function(num){
	for(var i = 1; i <= num ; i++){
		if(i * i === num){
			return true;
		}
	}
	
	return false;
}
```
- it works!
- But what is the problem here? for every input, I loop all the way to the num, that will take long time. Try a big number and see for yourself. 

- Since a number is a perfect sqaure if it's square root is less than half the number ..
- Meaning we can downsize the loop by half, let's try this

```
	if(num <= 1){
		return true;
	}
	
	for(var i = 1; i <= num /2 ; i++){
		if(i * i === num){
			return true;
		}
	}
	
	return false;
```

- it is better, but still takes long time for big numbers. 

- 1  = 1
- 4  = 1 + 3
- 9  = 1 + 3 + 5
- 16 = 1 + 3 + 5 + 7

Do you detect the pattern here? a square root is the sum of odd conseqative numbers less than the num itself
.. let's try this

```
	var isPerfectSqaure = function(num){
	var sum = 0
	
	for(var i = 1; i <= num  ; i++){
		if(i % 2 !== 0){
			sum += i;
			if(sum === num){
				return true;
			}
		}
	}
	
	return false;
}
```
- Sounds legit, it works .. now try a big number? It is still slow .. we need to 

- when sqaured number is larger than our number, then the num is not perfect sqaure and we should stop our loop.


	```
	// if number is one or 0
	if(num <=1){
		return true
	}
	
	// next smalled square and it's number
	var currentSquare = 4;
	var currentNum = 2;
	
	// loop while you're still less than num
	while(currentSquare <= num){
		// check if a match
		if(currentSquare === num){
			return  true;
		}

		//otherwise, get the next number
		currentNum++;
		//update currentSquare
		currentSquare = currentNum * currentNum;
	}
	
	return false;
	``` 
	
- woha! we have a solution. Try a big number? it is faster!

let's proof that with a timer. 
	