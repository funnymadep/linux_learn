# on my zsh + p10k 安装

### 1.安装zsh以及配置

```bash
    sudo apt update
    sudo apt upgrade
    sudo apt install -y zsh curl git vim
```

### 2.切换默认从bash为zsh
```bash
   chsh -s /bin/zsh  
``` 

### 3.安装p10k 和 on my zsh
```bash
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
    sh install.sh
```
### 4.设置p10k为默认主题

> 打开`~/.zshrc`

```bash
    vim ~/.zshrc
```

> 找到并将其修改 

> `ZSH_THEME="powerlevel10k/powerlevel10k"`

> 然后在终端输入

```bash
    . ~/.zshrc
    p10k configure
```
> 开始自定义自己的终端

### 5.安装高亮插件和自动补全插件

> 这些插件都很好用
    
> 下载插件并在~/.zshrc里添加插件

```bash
    git clone https://gitee.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions 
    git clone https://gitee.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    vim ~/.zshrc
```

> 找到并修改

`plugins=(git zsh-autosuggestions zsh-syntax-highlighting pip)`

> 最后`. ~/zshrc`
