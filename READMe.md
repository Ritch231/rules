### 2023年1月22日 首次使用git并提交clash规则
##### git

- 加入索引区
--加入单个文件或多个文件
gi
```bash
git add [file1 file2]
```



- 加入所有文件到索引区
git add .
- 删除文件
git rm
例如从索引区删除
git rm --cached test.lua
- 文件改名
git mv a.lua  b.lua

git commit -m "说明"
--查看日志
git log
git log --oneline -2

--比较修改内容
git diff
git diff --cached
tie
git checkout
--退出索引区
git reset HEAD test.lua


忽略文件
.gitignore
将文件名或者后缀添加进去，即可忽略管理

--更新最后的提交
git commit --amend

--返回过去
根据次序回退版本
git reset --hard HEAD
git reset --hard HEAD~
git reset --hard HEAD~2

根据id回退版本
--查看以前的commit_id
git reflog
git reflog -3 最近的条数

git reset --hard [commit_id]


#####分支
- 切换分支
git branch
git branch dev
git checkout

- 合并分支
git merge  dev
- 删除分支
git branch -d[name]