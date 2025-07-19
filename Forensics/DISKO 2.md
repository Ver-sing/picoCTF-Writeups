# Problem
Can you find the flag in this disk image? The right one is Linux! One wrong step and its all gone!
**Hint:**How can you extract/isolate a partition?

# Solution:
Extract the file with `gunzip disko-2.dd.gz`\
Check for partitions with `fdisk -l disko-2.dd`\
You will see two partitions (Linux and FAT32 file systems), extract them and check for the flag.  
Extract the first partition:  
`dd if=disko-2.dd of partition1.dd bs=512 skip=2048 count=51200`
Verify it; you should see something like "Linux rev 1.0 ext4".
`file partition1.dd`
Now, let's look for the flag:
`strings partition1.dd | grep -i "picoCTF"`

Flag: `picoCTF{4_P4Rt_1t_i5_90a3f3d1}`
PS: You can also try solving it using brute force with `strings disko-2.dd | grep -iE "picoCTF"`. Try the first 10 results.
