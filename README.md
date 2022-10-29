# transcrypt-for-noexec-fs
`transcrypt-for-noexec-fs` - patches for correct operation of [transcrypt](https://github.com/elasticdog/transcrypt) in file system where it is not possible to set the execution flag

## Steps:
1) Clone and install `transcrypt`
2) Clone and install patches:
```
$ git clone https://github.com/ZhymabekRoman/transcrypt-for-noexec-fs
$ cd transcrypt-for-noexec-fs
# Copy transcrypt_for_noexec_fs.patch to transcrypt directory and apply:
$ git apply transcrypt_for_noexec_fs.patch
```
3) Execute additional steps for `git` (optional)

**Important issue: manually run the `transcrypt pre_commit` command before each commiting! Because pre-commit hooks won't execute in noexec fs**

## Optional: additional steps for `git` in noexec file system
- `git config --global core.fileMode false`- if false, the executable bit differences between the index and the
       working copy are ignored; useful on broken filesystems like FAT.
- `git config --global --add safe.directory '*'`- by default, Git will refuse to even parse a Git config of a repository owned by someone else, let alone run its hooks, and this config setting allows users to specify exceptions, e.g. for intentionally shared repositories. Some file systems do not support ownership parameters
