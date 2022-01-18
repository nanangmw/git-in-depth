# What is Git?
git is a distributed version control system. at its core, git like a key value store, the value is the data and the key is hash of the data
Git store thing all in a git object (blob), git store compressed data in a blob with metadata in header and generate this data use SHA1.

# Git Commit
Commit point to a tree and it contains some other metadata :
 - Author and Committer
 - Date
 - Message
 - Parent Commit

Commit example :
```
>sample nanang$ tree .git/objects
.git/objects
├── 36
│   └── bfe4bb858b18824e35fa4948758d70c8fc5294
├── 58
│   └── 1caa0fe56cf01dc028cc0b089d364993e046b6
├── 98
│   └── 0a0d5f19a64b4b30a87d4206aade58726b60e3
├── info
└── pack

5 directories, 3 files
> sample nanang$ git cat-file -t 36bfe4
commit
> sample nanang$ git cat-file -p 36bfe4
tree 581caa0fe56cf01dc028cc0b089d364993e046b6
author nanang <nanang@jamtangan.com> 1642405649 +0700
committer nanang <nanang@jamtangan.com> 1642405649 +0700

Initial commit
> sample nanang$ git cat-file -t 581caa
tree
> sample nanang$ git cat-file -p 581caa
100644 blob 980a0d5f19a64b4b30a87d4206aade58726b60e3	hello.txt
> sample nanang$ git cat-file -t 980a0d5
blob
> sample nanang$ git cat-file -p 980a0d5
Hello World!
```


# Git Areas
Git have a 3 area:
- Working Area, The files in your working area (local) for free modify and that are not handled by git.
- Stagging Area, This area used for know change between current commit and next commit.
- Repository, This area contains all files you have committed in git.

# Stashing
One more place to store ur code in git to save uncommitted code. It's useful if you want to switch branches without committ.

Commands in git stash:
- ```git stash``` -->  Stashing your code
- ```git stash list``` --> Show your list stash
- ```git stash show stash@{n}``` --> Show content in your list stash
- ```git stash apply``` --> Spply content in your last stash
- ```git stash apply stash@{n}``` --> Spply your specific stash
- ```git stash --include-untracked``` -->  Stashing untracked files
- ```git stash --all``` --> Stashing all files
- ```git stash pop``` --> Delete last stashing and applying change
- ```git stash drop``` --> Delete last stash
- ```git stash drop stash@{n}``` --> Delete specific stash
- ```git stash clear``` --> Delete all stash


# Reference
Advanced GIT Nina Zakharenko [here](https://github.com/nnja/advanced-git)
