# HIT OSLab

哈工大[李治军操作系统](https://www.bilibili.com/video/av17036347)课程，基于 Linux 0.11 的 8 个实验。

项目的每个分支对应一个实验，master 分支为 Linux 0.11 原始代码。

## 如何运行本项目代码

- 使用该项目一键配置环境：[oslab-oneclick](https://github.com/CN-GuoZiyang/oslab-oneclick)
   ```bash
    git clone https://gitee.com/cn-guoziyang/oslab.git ~/oslab
    
    cd ~/oslab
    ./setup debian
   ```
- 配置完成后，用本项目替换`linux-0.11/`文件夹
   ```bash
    cd ~/oslab
    rm -rf ./linux-0.11
    git clone https://github.com/kcxain/HIT-OSLab.git ./linux-0.11
   ```
- 切换到对应实验的分支运行即可
   ```bash
    git checkout lab1
    cd ..
    ./run
   ```

## 实验内容

### Lab1：操作系统的引导
对应《Linux内核完全注释》的第 6 章，对计算机和 Linux 0.11 的引导过程有初步的了解
#### 一、改写`bootsect.s`主要完成如下功能：
1. `bootsect.s`能在屏幕上打印一段提示信息
    ```bash
    XXX is booting...
    ```
    其中 XXX 是你给自己的操作系统起的名字，也可以显示一个特色 logo ，以表示自己操作系统的与众不同。

#### 二、改写`setup.s`主要完成如下功能：
1. `bootsect.s`能完成`setup.s`的载入，并跳转到`setup.s`开始地址执行。而`setup.s`向屏幕输出一行
```bash
Now we are in SETUP
```
2. `setup.s`能获取至少一个基本的硬件参数（如内存参数、显卡参数、硬盘参数等）， 将其存放在内存的特定地址，并输出到屏幕上。
3. `setup.s`不再加载 Linux 内核，保持上述信息显示在屏幕上即可。