# Problem
Can the flag be found in this disk image? This time, it is not as plain as it seems!  
**Hint:** How would one search for and extract files from a partition?

# Solution
First, extract the file using `gunzip disko-3.dd.gz`.  
Next, inspect the file with `file disko-3.dd`, which reveals it is a FAT32 filesystem.  
Proceed to partition analysis with `fdisk -l disko-3.dd` (it is a single partition of 204800 sectors).

To search for the flag, use a raw search:  
`strings disko-3.dd | grep -i "picoCTF"`  
This reveals references to "picoCTF-2025" in a file.

Mount the disk image:
```bash
sudo mkdir /mnt/disko
sudo mount -o loop disko-3.dd /mnt/disko
```
List the files:
```bash
ls -la /mnt/disko
```
This shows three directories. Upon further inspection with `ls -la /mnt/disko/log`, several files are listed, including one called "flag.gz".

Extract the flag:
```bash
cp /mnt/disko/log/flag.gz
gunzip flag.gz
cat flag
```
Alternatively:
```bash
zcat /mnt/disko/log/flag.gz
```

**Flag:** `picoCTF{n3v3r_z1p_2_h1d3_7e0a17da}`

