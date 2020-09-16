# Git 的分支管理

### 创建一个新的分支

```bash
git branch newbranch;//创建一个名为 newbranch 的新分支
git checkout newbranch;//切换到 newbranch 分支
```

上面的两条命令可以简写为：

```bash
git branch -b newbranch;//创建一个新分支并切换到该分支
```

此时，可以对文件进行修改，包括：添加新文件，修改已存在文件，删除已存在文件。例如：

```bash
code new_file.md;//使用 vs code 新建一个名为 new_file 的文件
git add .;//将所有修改放入暂存区
git commit -m "new_file";//提交修改
```

> 请注意，每次在新分支修改完文件后，请务必记得提交修改。否则，两个分支会混同。
>
> 创建新分支后，所有的修改在切换回 主分支（master） 之后，都会被还原回创建新分支之前的状态。例如，在新分支创建新文件并提交修改，此时切换回主分支会发现，在新分支创建的文件消失了。在切换回新分支之后，新文件又会再次出现。
>
> 在新分支删除文件后，请务必记得在提交之前先将修改放入暂存区。

### 合并并删除分支

当处理完分支的事项后，想要将分支里的更改合并到主分支里，可以执行：

```bash
git switch master;//切换到主分支
git merge newbranch;//合并新分支到主分支
```

> 合并将会把在新分支内做的所有修改，包括对主分支的修改合并到新的主分支（其实并不是新的主分支，只是指针改变了位置）。

当新分支完全完成了他的使命，可以执行下面的命令来删除此分支：

```bash
git branch -d newbranch
```

### 处理分支的冲突

有的时候会在不同的分支上工作。当完成需要处理的问题并合并各分支之后，可能分支之间会有冲突，此时 `Git` 会打印冲突信息：

```bash
Auto-merging branch-new.md
CONFLICT (content): Merge conflict in branch-new.md
Automatic merge failed; fix conflicts and then commit the result.
```

此时，打开冲突文件，可能会有如下显示：

```bash
new branch first
<<<<<<< HEAD
new files(con)(–flick del)
=======
new files(conflick)(new)
>>>>>>> branch-2

merge



merge branch-3 new

new file
```

上面的 行 2 到行 6 显示出了冲突的所在。`=======`  以上为当前分支的修改情况，以下为 `branch-2` 的修改情况。你可以自行决定要保留哪些修改。例如我们保留当前分支的修改。之后，提交至暂存区 –> commit –> 合并分支。

 ### 管理分支

新建，切换，合并，删除这些操作已经看过了，还有一些其他的命令也是需要了解的。

```bash
git branch;//查看所有分支
git branch -v;//查看所有分支的最后一次提交
git branch --merged;//查看所有亦被合并的分支
git branch --no-merged;//查看所有未被合并的分支
```