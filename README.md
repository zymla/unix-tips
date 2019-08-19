# unix-tips

## Tar
### UTF-8 filenames and Windows
Add `--format=posix` when creating the  file, e.g.:
```
tar --format=posix -z -v -c -f ~/json.tgz path/*.json
```
### CD into directory before tar action, e.g. keep only part of path in tar
```
tar -cvfz foo.tgz -C /dir/to/cd/into sub/path/with/files
```
