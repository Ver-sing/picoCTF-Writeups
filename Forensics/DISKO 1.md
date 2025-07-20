# Problem
Can the flag be found in this disk image?  
**Hint:** Maybe the strings command could help. If only there were a way to use it.

# Solution
First, extract the file using `gunzip disko-1.dd.gz`.  
Then, search for the flag with the following command:  
`strings disko-1.dd | grep -i "picoCTF"`

Flag: `picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}`