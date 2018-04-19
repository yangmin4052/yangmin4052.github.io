---
title: Linux命令
date: 2017-12-09 19:53:07
tags:
---

```
whoani
hostname
uname -n
w
```

man 手册
```
ls --help
man ls
```

安装man
```
yum -y install man
```
```
/-l
```

```
-l 
-a
-h
-d
-F
-t 
-r
-R
-S
-i
--file-type
--full-time
```

```
ll 
ls -l
```

```
ls -a
```

```
ls -l -h
ls -lh
```

```
ls -lhk
```

```
ls -l dir
ls -l -d dir 
ls -lt
ls -ltr
ls -lR dir
tree dir
ls -R dir
ls -Rl dir
ls -l
ls -l --full-time
ls -lS
ls -lSr
```

mkdir
```
mkdir -p a/b/c/d
ls -R
tree
mkdir -m ???
mkdir 'hello world'
mkdir hello_world
```

```
touch test.log
touch -d '20101010000000' test.log
```

```
cat test.log
cat -b test.log
cat -n test.log
cat -A test.log
```

```
less services
```
space键 下一页
ctrl+c键 退出

```
more services
```

```
head services
head services | nl
head -n 20 services
head -20 services
```

```
tail services
tail -n 15 services
tail -15 services
tail -1000 test.log | more
tail -f test.log    实时
```

```
cd  打开家目录
cd ~    打开家目录
cd ..   打开上级目录
cd /    打开根目录
cd -    打开上一个目录
ls$(cd -)
```

```
su ???
pwd 查看路径
mkdir ~/log 在家目录创建log文件夹
ls ~/   
ln -s /data/bbs_log /root/test/a/dir/bbs_log 软链接
        原目录 新目录
pwd -P
tree -l 1
```

```
find /  非特殊情况，不要这么做，太耗时间
find ./ -name services
find ./ -iname services 忽略大小写
find . -type f
find . -type d
```

cp 拷贝
```
cp test.log test.log.bak
cp -rf c c_dir
```

mv
```
mv test.log t-test.log
```

```
zip -r all.zip ./
unzip -l all.zip
unzip all.zip
unzip -o all.zip
```

```
tar zcf
tar zvf
tar zxf all.tar.gz
tar zxf all.tar.gz -C bbb/
```

```
find /etc -size +5w -type f
ls -lh ???
find . empty
find . ! -empty
```

管道符 |
转义符 \
单引号 ''
双引号 ""

echo
```
echo -e
echo -e 'ni \v hao \v a'
echo -n 'nihao'
```

>   覆盖
>>  追加
```
echo ' ' > services
echo ' ' >> services
```

grep    截取
-v  排除
```
egrep -v '^$|^#' a.txt
grep -E -v '^$|^#' a.txt
-l
awk ???
set ???
```

```
yum -y install lrzsz
rz
sz
clear
ctrl+l键
md5sum
sha1sum
ls -l
ll
alias 别名
\cp a.txt b.txt
top
```

```
ifconfig
cd /etc/sysconfig/network-scripts/
ping www.baidu.com
vi /etc/re
cat /etc.resolve.conf
114.114.114.114
ip a
free -m
free -g
df -h
du -sh /*
```

```
ctrl+a  到最前
ctrl+e  到最后
ctrl+u  删前面
ctrl+k  删后面
```

```
vi
a   输入
ESC
o
O
gg 
GG
yy
P
wq！
:set nu
:%s/hoo/HAO/g
:2.5s/HAO/hao/g
