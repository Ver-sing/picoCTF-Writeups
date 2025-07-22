# Problem
Files can always be changed in a secret way. Can you find the flag? 
**Hint 1:** Look at the details of the file
**Hint 2:** Make sure to submit the flag as picoCTF{XXXXX}  

# Solution
Use `exiftool cat.jpg` to look into the file information. In the license field, you will see base64-encoded text; copy it.  
Then decode it with this command:  
`echo -n 'cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9' | base64 --decode`  
You can also use any online base64 decoder.  

**Flag:** `picoCTF{the_m3tadata_1s_modified}`

