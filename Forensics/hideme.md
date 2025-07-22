# Problem
Every file gets a flag.  
The SOC analyst noticed one image being sent back and forth between two people. They decided to investigate and discovered that there was more than meets the eye.

# Solution
Use `zsteg flag.png`, which will show something like "3206 bytes of extra data after image end" and also display the extra data. This data contains "secret/flag.png", indicating there is a directory inside with another image.  
Let's extract it:  
`binwalk flag.png`  
or  
`dd if=flag.png bs=1 skip=$((0x9b3b)) of=extract.zip`  
Now just extract the zip using `unzip extract.zip`.  
Navigate to the "secret" folder, where you will find an image containing the flag.  

**Flag:** `picoCTF{Hiddinng_An_imag3_within_@n_ima9e_82101824}`

