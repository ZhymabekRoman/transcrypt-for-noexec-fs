# transcrypt-for-noexec-fs
`transcrypt-for-noexec-fs` - patches for correct operation of transcrypt in file system where it is not possible to set the execution flag

## Another useful steps for git in noexec file system
- `git config --global core.fileMode false`- if false, the executable bit differences between the index and the
       working copy are ignored; useful on broken filesystems like FAT.
- `git config --global --add safe.directory '*'`- by default, Git will refuse to even parse a Git config of a repository owned by someone else, let alone run its hooks, and this config setting allows users to specify exceptions, e.g. for intentionally shared repositories. Some file systems do not support ownership parameters
