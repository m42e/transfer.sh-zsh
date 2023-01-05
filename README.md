# Advanced transfer.sh script for ZSH

For [transfer.sh](https://github.com/dutchcoders/transfer.sh)

# Usage

```
source transfer
transfer [-d <d>] [-t <n>] [-q/-s] [-p [<password>]] <file/dir>
```

```
Usage of transfer

transfer [-t <n>] [-d <d>] [-p <s>|-e] <filename/folder>

--times/-t <n>      limit to n downloads
--days/-d <n>       limit to n days
--password/-p <s>   encrypt the file with a password (gpg required)
--encrypt/-e        encrypt using gpg and a generated password
-q/-s               only print download url to stdout,
                    use -qq/-ss to disable progress
```
