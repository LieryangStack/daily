# github个人主页

## 环境安装

1. 安装 Jekyll

```sh
sudo apt-get install -y ruby-full build-essential zlib1g-dev
```

2. 添加环境变量

```sh
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

<span style="background-color: pink">不进行环境变量设置可能会有以下问题：

![Alt text](<./image/Screenshot from 2023-11-09 18-18-48.png>)

3. 安装 Bundler 

```sh
gem install jekyll bundler
```

安装成功

![Alt text](<./image/Screenshot from 2023-11-10 16-25-04.png>)

## 本地构建