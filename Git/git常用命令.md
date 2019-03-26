# Git 常用命令及常见问题

### 常用命令：





























### 常见问题：

[error: src refspec master does not match any. 错误处理办法](https://www.cnblogs.com/jeremylee/p/5715289.html)

```bash
$ git pull --rebase origin master
warning: no common commits
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From github.com:hahah/ftpmanage
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> origin/master
First, rewinding head to replay your work on top of it...
Applying: init files
```

1. 重新建立当前目录的远程master仓库

```bash
$ git pull --rebase origin master
```



$ git pull --rebase origin master