# CruisePack
STS cruise data packer, in Python

Take the contents of a directory and turn each supplied argument
into a `.tar.bz2` (or `.zip`), `.md5.txt` and `log.txt` file. If
you are archiving a dataset of <=10GB (likely), it is recommended you
run this script in `screen`.

## Examples

### Just source argument(s)
 ```
cruisepack -s /share/cruise/foo/BAR1213 /share/cruise/foo/BAZ1214
```
   ... would make:
1. `/share/cruise/foo/BAR1213.tar.bz2`
2. `/share/cruise/foo/BAR1213.log.txt`
3. `/share/cruise/foo/BAR1213.md5.txt`
4. `/share/cruise/foo/BAZ1214.tar.bz2`
5. `/share/cruise/foo/BAZ1214.log.txt`
6. `/share/cruise/foo/BAZ1214.md5.txt`

In this example, it would be up to the user to delete
`/share/cruise/foo/BAR1213` and `/share/cruise/foo/BAZ1214` in an
effort to clean up disk space.

### With `--delete-after` and `.zip` extension
 ```
cruisepack -E zip -D -s /share/cruise/foo/BAR1213 /share/cruise/foo/BAZ1214
```
   ... would make:
1. `/share/cruise/foo/BAR1213.zip`
2. `/share/cruise/foo/BAR1213.log.txt`
3. `/share/cruise/foo/BAR1213.md5.txt`
4. `/share/cruise/foo/BAZ1214.zip`
5. `/share/cruise/foo/BAZ1214.log.txt`
6. `/share/cruise/foo/BAZ1214.md5.txt`

In this example, `/share/cruise/foo/BAR1213` and
`/share/cruise/foo/BAZ1214` would be recursively deleted after being
archived. *USE WITH CARE*.
