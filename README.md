# unix-tips

## Tar
### UTF-8 filenames and Windows
Add `--format=posix` when creating the  file, e.g.:
```
tar --format=posix -z -v -c -f ~/json.tgz path/*.json
```
