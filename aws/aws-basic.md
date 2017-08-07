# AWSの基礎など
## 参考文献
- http://qiita.com/naoki_mochizuki/items/814e0979217b1a25aa3e
- http://qiita.com/na0AaooQ/items/5bd62e630a2faf051a52

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
