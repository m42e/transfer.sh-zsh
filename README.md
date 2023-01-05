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
--recipient/-r <s> encrypt for recipient
--password/-p <s>   encrypt using gpg and the specified password
--encrypt/-e        encrypt using gpg and a generated password
-q/-s               only print download url to stdout,
                    use -qq/-ss to disable progress

Environment:
 - TRANSFER_BASE_URL     The baseurl of the transfer server,
                         default transfer.sh
 - TRANSFER_TRANSFORMER  Default is cat, which is replaced by
                         a proper gpg call, if -r/-e/-p is
                         specified, default is cat
```


# Special options (environment)

You can set the `TRANSFER_BASE_URL` to point to your transfer.sh instance.
By default the content is not transformed before uploading (just piping it through cat), `TRANSFER_TRANSFORMER` could be set to perform any command which accepts stdin and outputs on stdout to transform the data on-the-fly.
This mechanism will also be used for GPG encryption. e.g. you could perform a rot13 operation, by the following two lines:

```
export TRANSFER_TRANSFORMER="tr 'A-Za-z' 'N-ZA-Mn-za-m'"
transfer README.md
```

Or any other encrypting call.

Consider this not as real feature, but more a thing to play around :)
