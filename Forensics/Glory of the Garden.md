# Problem
This garden contains more than it seems.
**Hint:** What is a hex editor?

# Solution
The flag is in the hex dump of the file. You can use any online hex editor to view it, or just use this command:
`strings garden.jpg | grep -i "pico"`

**Flag:** `picoCTF{more_than_m33ts_the_3y3657BaB2C}`

