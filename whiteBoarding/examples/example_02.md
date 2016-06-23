## Example 02
### Problem
#### Question
Given an array of distinct integer values, count the number of pairs of intergers that have the difference k between them.

#### For example
[1,7,5,9,2,12,3] and difference k = 2
the pairs with difference of 2 are (1,3), (7,9), (5,7) and (3,5).

### Solution
#### Brute Force
- init a pairs array to hold the resulting pairs.
- go thru the array
- hold the first item
- compare it to every other item in the array
- look if the current item is +k than the initially held value.
- if so, add the pair to pairs array
- else, continue to the next item. 
- once done with the loop for the current item, get the
next item and so on.

```
function differenceK(arr, k){
	var count = 0;
	for(var i = 0; i < arr.length; i++){
		console.log(i,arr[i]);
		
		for(var j= 0; j < arr.length; j++){
			console.log(arr[j]);
			if(arr[j] - arr[i] === k){
				count++
				console.log('count is: ', count, 'and pair is', arr[i] ,arr[j]);
			}
		}
	}
}

differenceK([1,7,5,9,2,12,3],2);
```