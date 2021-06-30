# unix-tips
## Git
```
git config --global user.email "email@domain"
git config --global user.name "Name"
git config --global credential.helper store
```


## Tar
### UTF-8 filenames and Windows
Add `--format=posix` when creating the  file, e.g.:
```
tar --format=posix -z -v -c -f ~/json.tgz path/*.json
```
### Pipe list files to tar
```
find . -maxdepth 1 -iname 'file*' -mtime -1 | sort | tar cvfz tarfile.tgz -T -
```

### CD into directory before tar action, e.g. keep only part of path in tar
```
tar -cvfz foo.tgz -C /dir/to/cd/into sub/path/with/files
```
## `xargs`
### gsutil cp all ipynb files
`ls -1  *.ipynb| xargs -I "{}" gsutil cp "{}" "gs://<BUCKET_NAME>/$HOSTNAME/$(date -I)/{}"`

## Convert Latin1 to UTF-8
`iconv -f iso-8859-1 -t utf-8 input_file -o ouput_file`

## Add line numbers
`cat -n`

# Unicode
## Remove BOM from Excel CSVs
`sed '1s/^\xEF\xBB\xBF//'`
