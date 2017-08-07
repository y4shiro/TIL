# AWSの基礎など
## 参考文献
- http://qiita.com/naoki_mochizuki/items/814e0979217b1a25aa3e
- http://qiita.com/na0AaooQ/items/5bd62e630a2faf051a52
- http://qiita.com/oishihiroaki/items/bc663eb1282d87c46e97

## EC2の立ち上げ方
### インスタンスの作成
### ディストリビューションを選択
### ネットワークなど設定
### タグも設定

## EC2に接続

## Rubyに必要な物インストール
```bash
yum -y install gcc-c++ glibc-headers openssl-devel readline libyaml-devel readline-devel zlib zlib-devel libffi-devel libxml2 libxslt libxml2-devel libxslt-devel sqlite-devel
```

## Git
```bash
$ sudo yum install git
```

### GitHubとの接続
鍵生成して、共有鍵をGitHubに登録する
```bash
$ mkdir .ssh
$ chmod 700 .ssh
$ cd .ssh
$ ssh-keygen -t rsa
-----------------------------
Enter file in which to save the key ():aws_git_rsa 
(#ここでファイルの名前を記述して、エンター)
Enter passphrase (empty for no passphrase): 
(#何もせずそのままエンター)
Enter same passphrase again: 
(#何もせずそのままエンター)
-----------------------------

$ vim config
-----------------------------
# githubの場合以下を追記
Host github
  Hostname github.com
  User git
  IdentityFile ~/.ssh/aws_git_rsa (#秘密鍵の設定)
-----------------------------

$ chmod 600 config
```

下記コマンドを実行して、正常に動作が行われると接続完了。  
```bash
$ ssh -T github
# Hi **** You've succwwwessfully authenticated, but GitHub does not provide shell access.
```

## Node.js
```bash
$ git clone https://github.com/creationix/nvm.git ~/.nvm
$ source ~/.nvm/nvm.sh
```

```bash
$ vim .bash_profile
```

```bash
# nvm
if [[ -s ~/.nvm/nvm.sh ]] ; then
        source ~/.nvm/nvm.sh ;
fi
```

```bash
$ nvm install 7.10.1
$ nvm use v7.10.1
$ node -v
```


## rbenv
```bash
$ git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
$ source .bash_profile
$ git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
$ rbenv rehash
```

### rubyのインストール
```bash
$ rbenv install -v 2.4.1
$ rbenv global 2.4.1
$ rbenv rehash
$ rbenv -v
```

## Rails環境構築
## node環境構築

## RDSの立ち上げ方
## ELB(Elastic Load Balancing)の設定など
## ElastiCacheの立ち上げ方
