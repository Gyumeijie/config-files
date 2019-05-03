# The .gitattributes file

Solve the diff visual problems on your pull request. Or select an automatic action when you have conflicts merging your branchs. For example your images, lock files, etc.

One of the most important file on your repository is `.gitignorebut` we have also another useful file: `.gitattributes`.

`.gitattribes` is used to help Git understand the file contents to better diff/render it. Used for merge resolution strategy (default, union etc.) as well.

## Most common uses on .gitattributes

### export-ignore
All files declared with export-ignore will be omitted when repository is **downloaded**.

```
# Ignore all test and documentation with “export-ignore”.
.gitattributes export-ignore
.gitignore export-ignore
README.md export-ignore
/docs export-ignore
/tests export-ignore
```

### text=auto and binary
Handle `line endings` automatically for files detected as **text**. Also, all files detected as **binary**(like an .jpeg file) will be handled untouched. `auto` perform LF normalization.

```
* text=auto
*.php text
*.png binary
*.jpg binary
```

### merge
It's possible to set a deffault descision when conflicts appear: default, ours, then.

```
# Some developers uses these, I prefer -diff for mistakes prevention
yarn.lock merge=ours
package-lock.json merge=ours
```

### diff
Do not try and `merge` these files.

```
yarn.lock -diff
*.map -diff
```