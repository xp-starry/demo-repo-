```shell
在vscode中打开某一文件夹，在菜单栏 -> 查看 -> 终端	
git clone git@github.com:xp-starry/demo-repo-.git
第三部分对应于github repository中的 code ssh所提供的链接

cd:切换目录
dir：列出目录中的所有内容
	ls -la	可以简写为	la	mac中列出目录中的所有内容（包含隐藏目录/文件）
	
git status
展示所有已更新，创建或删除但尚未保存在提交中的文件
```

```shell
PS D:\xiaopeng\learnGit\demo-repo-> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        git.md
        index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

```shell
git add .			跟踪当前目录下的所有文件（未跟踪部分和已修改部分）通过git暂存
git add index.html	跟踪单独文件/文件夹
```

```shell
PS D:\xiaopeng\learnGit\demo-repo-> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   git.md
        new file:   index.html
```

在github中编写document然后提交时有两个框：标题和描述，以下命令中两个 **-m** message与之一一对应！！！

```shell
PS D:\xiaopeng\learnGit\demo-repo-> git commit -m "Added index.html and git.md" -m "some description"
[main c57918b] Added index.html and git.md
 3 files changed, 5 insertions(+)
 create mode 100644 git.md
 create mode 100644 index.html
```

推送远程仓库：

```
git push
```

SSH KEY

邮箱地址必须于登录github账户的地址相同，点击Enter
第三行：后可以修改保存的文件名

```shell
C:\Users\xiaop>ssh-keygen -t rsa -b 4096 -C "xiaopen.li@outlook.com"
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\xiaop/.ssh/id_rsa): testkey
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in testkey		私钥
Your public key has been saved in testkey.pub		公钥（上传到github）
The key fingerprint is:
SHA256:n0+ws3C3QwatDsUheDX5yUtURTzSani9LgZ0h/kelcU xiaopen.li@outlook.com
The key's randomart image is:
+---[RSA 4096]----+
|       . .o. .o=o|
|      . o o... oE|
|       . o *..* +|
|          +o*B +.|
|        S.o++.o o|
|        ...=+  + |
|        .o*o+ o .|
|         o.*.+ o |
|          . +..  |
+----[SHA256]-----+
```

公钥与私钥的工作原理：将公钥放在github上，然后每次想要连接到github或在github上推送代码或通过本地机器使用您的账户时，都可以使用私钥向github表明您是生成此公钥的人

