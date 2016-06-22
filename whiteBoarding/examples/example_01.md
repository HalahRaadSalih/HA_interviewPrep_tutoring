## Example 1

Write a function that reverses a string. 

### Steps
1. Understand the probelm. What is the problem here? reversing a string. But, it says a function which means it needs an input and an output. (Write this down in your notes on the side). Ask if you can use any of javascript bulit in functions like split or join.
2. A simple example: Your name. David, turn David into divaD.
3. You may ask yourself if uppercase or lowercase matter here, I'd say they don't in this case but I recommend to keep the same state of the letter. 
4.  Data structure, what would you use to hold the result? Another string, an array or an object? Why ? 
5. Algorithm. How do you reverse a string? What changes when you reverse a string?
6. Explain your solution here with words before coding.
7. Write the code and talk as you write.
8. Verify your code by trying out your example, David. 
9. Check for errors and edge cases. What if it wasn't a string? what if there is not input? what if the input is one letter? what if the input is a squequence of the same letter?
10. What is the run time? Space complexity?
11. Alternative implementaion?
12. Maybe change the data structure? 


### Solution #1
- this solution assumes that you're not using built in javascript methods.
- creating a function with a name indicating the job
- set the input and output.
- creating a new string variable called a reversedStr to hold the result of reversing a string.
- loop thru the input string and concat the last letter of the string to the reversedStr.
- you could loop backwords too. 
- return the reverseString
- try out your example: David
- works? 
- Try another example, does it work? You have a working solution.

```
function reverseString(str){
	var reversedStr = '';
	
	for(var i = 0; i < str.length; i++){
		reversedStr += str[str.length -1 -i];
	}
	
	return reversedStr;
}

reverseString('david');
```
### Problems with the solution
- Using concatenation would result in a new string being created in memory upon each iteration - as strings are immutable objects.