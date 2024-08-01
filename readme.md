# 版本控制

[TOC]

## 一、基本命令

```
# 初始化
git init
# 管理指定文件,
git add 文件名或者.
# 生成版本
git commit -m “描述信息”
# 查看版本
git log 
# 回滚之后，查看版本
git reflog
# 回滚到具体版本
git reset --hard 版本号
```

## 二、分支

```
# 查看分支
git branch
# 创建分支
git branch 分支名称

# 切换分支
git checkout 分支名称

# 合并分支
git merge 要合并的分支

# 删除分支
git branch -d 分支名称
```



## 三、个人信息配置，只配置一次即可

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```



## 四、上传远程仓库

```
# 给远程仓库起别名
git remote add origin(起个别名) 远程仓库地址

# 向远程仓库推送代码
git push origin 分支

# 克隆远程仓库代码
git clone 远程仓库地址
# 切换分支
git checkout 分支

```



## 五、使用git上传本地代码到github

（github自2021年，不再支持通过账户密码的方式进行git

push）

**采用ssh的方式**

### 1. 在本地配置个人信息

（如果配置好，则省略）

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

### 2. 在本地生成[SSH](https://docs.github.com/zh/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

- 打开终端。
- 粘贴以下文本，将示例中使用的电子邮件替换为 GitHub 电子邮件地址
- `ssh-keygen -t ed25519 -C "your_email@example.com"`
- 直接按两个enter，设置为默认即可
- 最后得到了两个文件：id_rsa和id_rsa.pub
- 查看id_rsa.pub公钥：`cat ~/.ssh/id_rsa.pub`

- 在github上，添加ssh秘钥

  - 将 SSH 公钥复制到剪贴板：打开id_rsa.pub文件，并且复制全部内容
  - 在 GitHub 任意页的右上角，单击个人资料照片，然后单击“**设置**”。
  - 在边栏的“访问”部分中，单击 “SSH 和 GPG 密钥”。
  - 单击“新建 SSH 密钥”或“添加 SSH 密钥” 。
  - 在 "Title"（标题）字段中，为新密钥添加描述性标签。 例如，如果使用的是个人笔记本电脑，则可以将此密钥称为“个人笔记本电脑”。
  - 选择密钥类型（身份验证或签名）。 有关提交签名的详细信息，请参阅“[关于提交签名验证](https://docs.github.com/zh/authentication/managing-commit-signature-verification/about-commit-signature-verification)”。
  - 在“密钥”字段中，粘贴公钥。
  - 单击“添加 SSH 密钥”。
  - *如果出现提示，请确认你的帐户是否拥有 GitHub 访问权限。 有关详细信息，请参阅“[Sudo 模式](https://docs.github.com/zh/authentication/keeping-your-account-and-data-secure/sudo-mode)”。*

- 本地通过git上传

  - 首先通过git添加远程仓库，注意是ssh地址

    ```
    git remote add origin(起个别名) 远程仓库地址
    ```

    然后向远程仓库推送代码

    ```
    git push origin 分支
    ```

    

    
