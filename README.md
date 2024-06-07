[![asciicast](https://asciinema.org/a/IKT7Ha30YG5ond1ofk87zX2Yg.svg)](https://asciinema.org/a/IKT7Ha30YG5ond1ofk87zX2Yg)
### Step1. Linux安装所需的函数库

1. 进入Terminal终端，输入以下命令安装库函数，使用密码授予安装权限
```
sudo apt-get install libevent-dev libboost-system-dev libboost-filesystem-dev libboost-test-dev libboost-program-options-dev libboost-thread-dev libfmt-dev libdb-dev libdb++-dev openssl -y
sudo apt install libnorm1,libpgm-dev,libzmg5 -y
sudo apt install screen -y
```
2. 建立项目文件夹，下载必要程序
```
cd
mkdir zrcoin && cd zrcoin
wget https://solomining.s3.ap-northeast-1.amazonaws.com/zrcoin.conf
wget https://solomining.s3.ap-northeast-1.amazonaws.com/zrcoind
wget https://solomining.s3.ap-northeast-1.amazonaws.com/zrcoin-cli
wget https://solomining.s3.ap-northeast-1.amazonaws.com/miner.sh
```

[![asciicast](https://asciinema.org/a/PoS3FJWicvzrx5lSXeBVnJkD7.svg)](https://asciinema.org/a/PoS3FJWicvzrx5lSXeBVnJkD7)
### Step2. 启动zrcoind，初始化程序目录

注：以下操作均在zrcoin文件夹内进行
```
sudo ./zrcoind --printtoconsole
```
运行大约5秒后，屏幕正确输出代码后，使用组合键 Ctrl+C 关闭程序，此时程序目录已建好

* 拷贝配置文件到目录下
```
cp zrcoin.conf ~/.zrcoin/zrcoin.conf
```

* 启动节点程序
```
screen -S zrcoin
sudo ./zrcoind --printtoconsole
使用组合键 Ctrl+A 然后按 D 使其进入后台运行
```

* 启动挖矿程序
```
screen -S miner
sh miner.sh
使用组合键 Ctrl+A 然后按 D 使其进入后台运行
```

[![asciicast](https://asciinema.org/a/10XD17qMMOL7FRJ5O1DAe2wng.svg)](https://asciinema.org/a/10XD17qMMOL7FRJ5O1DAe2wng)
### Step3. 拍摄视频

拍摄视频前，首先切换zrcoin进程到前台，使用以下命令
```
screen -r zrcoin
```
此时屏幕显示区块运行和挖矿状态，摄像头此时可启动进行录制。录制结束后，输入组合键 Ctrl+A 然后按 D 使进程返回后台运行
