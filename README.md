# Palindrome_Permutation

Inspiration from Educative.io "Write an efficient method that checks whether any permutation ↴ of an input string is a palindrome" https://www.interviewcake.com/question/java/permutation-palindrome?course=fc1&section=hashing-and-hash-tables


Write an efficient method that checks whether any permutation ↴ of an input string is a palindrome. ↴

You can assume the input string only contains lowercase letters.

Examples:

"civic" should return true
"ivicc" should return true
"civil" should return false
"livci" should return false
"But 'ivicc' isn't a palindrome!"

If you had this thought, read the question again carefully. We're asking if any permutation of the string is a palindrome. Spend some extra time ensuring you fully understand the question before starting. Jumping in with a flawed understanding of the problem doesn't look good in an interview.



Questions about the Questions
------------------------------------------
- Just to confirm, I will iterate through variations of the word to see if there is a palindrome? How many variations? All permuatutions or just some?
- Should I consider subpermuatations? I see that ivicc is true. 
- Will there be spaces, if so how will this be handled? 
- How is the information passed through?

Assumptions
------------------------------------------
- Only lowercase letters
- All possible permutations of the word. 
- If there are duplicate letters we can remove the permutations that look exactly the same to save time.. this may be hard to do
- Consider all permutations

Ideas 
-------------------------------------------
- We can review the original to see if this is a palindrome. Then we can move the first letter through the list in each position. Then put it back in original spot and move the remaining letters through all the positions. This would use recursion and could potentially be heavy on memory and time O(n!n) no matter what. 

soul --> First letter in first position
solu --> Swap last two and work way back to first letter - do this n length time
slou --> Swap the second last with the one in front  repeat till you get to start. 
sluo --> At start. Go back and swap last two and work way back to start
sulo --> Repeat 
suol --> If you were to swap the middle two you would go back to soul. 

osul --> Switch to next letter and leave it in front
oslu
olsu
.........

- The next item to consider is if we have duplicate characters and if so how many? We would then be able to make substrings at a minimum out of the duplicate values. This would bring our best case time to O(n) meaning we would have to iterate through the string once. If there were no matches we would return false. If there were we would investigate further by seeing the count and which values had a double.. perhaps a string holding the duplicate character? We would know based on the number of duplicates how many palindromes permutations we would have. We will need a special case if it is blank and if there is one letter.

Example 1: Soul - No duplicate characters = False 
Example 2: MOM - Has duplicate M. only 1 permutation = True



Test Cases 
--------------------------------------------
- 1 letter phrase 
- blank/null 
- non-string 
- spaces




