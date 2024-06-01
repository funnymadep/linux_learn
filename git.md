
# github 一些用法

---

## git 初始化本地新建仓库

```bash
git init
git remote add origin git@github.com:git@github.com:funnymadep/linux_learn.git
git add .
git commit -m "first commit"
git branch -M main
git push -u origin main
```

## git clone 选中分支

```bash
git clone -b <branch-name> <repository-url>
```

## git checkout 创建并切换分支

```bash
git checkout -b <new-branch-name>
```

## 解决分支冲突

```bash
git fetch origin main
git merge origin/main
```

***或者***

```bash
git pull origin main
```

***这两句用法是一样的***

## ssh公钥

生成并查看公钥
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
cat ~/.ssh/id_rsa.pub
```

***可能也需要配置config防止端口错误***
```bash
# Just for clone
Host github.com
HostName ssh.github.com
Port 443
User git
```
