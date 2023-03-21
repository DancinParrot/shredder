# Shredder
A file shredder written in nim, that attempts to mimic the [DoD 5220.22-M Standard data erasure method](https://www.bitraser.com/article/DoD-5220-22-m-standard-for-drive-erasure.php).

## How it works
- A file and a number of passes/cycle should be specified (default is 1 pass).
- A file will be overwritten with zeroes, ones, and then random bytes (a complete cycle/pass). 
- After which, the file will be deleted.

## Compile
Windows:
```Bash
nim c -d=mingw -d:release shredder.nim
```

## Disclaimer
Do note that this tool does not guarantee that your data is 100% erased, though any means of data recovery will still be inconvenient and highly time-consuming. DoD's method as mentioned above is meant for a erasing the entire drive, but this tool only adapts and applies the method on a given file. Moreover, there are many factors that may result in an incomplete data erasure, such as file systems with redundancy, cached data .etc, as mentioned in the official man page for the Linux [shred](https://linux.die.net/man/1/shred) tool. As such, DO NOT use this tool to erase highly sentitive and confidential data.