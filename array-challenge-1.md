# Array Challenge
Have the function ArrayChallenge(arr) take the array of integers stored in arr 
which will always contain an even amount of integers, 
and determine how they can be split into two even sets of 
integers each so that both sets add up to the same number. 
If this is impossible return -1. If it's possible to split the array into two sets, 
then return a string representation of the first set followed by the second set with 
each integer separated by a comma and both sets sorted in ascending order. 
The set that goes first is the set with the smallest first integer. 

For example: 

if arr is [16, 22, 35, 8, 20, 1, 21, 11], 
then your program should output 1,11,20,35,8,16,21,22 

Once your function is working, take the final output string and concatenate it with your ChallengeToken, 
and then replace every third character with an X. 

> Your ChallengeToken: 67kseucpjbd


Examples
```
Input: array(1,2,3,4) 
Output: 1,4,2,3 
Final Output: 1,X,2X36XksXucXjbX
```
```
Input: array(1,2,1,5) 
Output: -1 
Final Output: -1X7kXeuXpjXd
```
