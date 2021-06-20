# SaTC
A prototype of Shared-keywords aware Taint Checking, a novel static analysis approach that tracks the data flow of the user input between front-end and back-end to precisely detect security vulnerabilities.


完整代码环境正在整理中...

## 临时代码结构使用与说明

### 目录说明
- satc_front : 前端提取模块
- satc_TaintCheck : 污点分析引擎

### 运行环境准备

#### satc_front
1. 进入`satc_front/jsparse`

2. 如果有安装node.js环境，运行`npm run start`即可;
   如果没有node.js环境，使用docker运行以来环境：
    > docker build . -t jsparse

    > docker run -itd 3000:3000 jsparse

运行方法:
[satc_front/readme.md](satc_front/readme.md)


#### satc_TaintCheck
**目前需要从dockerhub上拉取依赖环境的镜像**
> docker pull cpegg/satc:1.2.0

运行方法:
> time python tool/main.py \<path to binary> \<path to ghidra result>

example：
> time python tool/main.py test/R7000P-V1.3.0.8/httpd test/R7000P-V1.3.0.8/httpd_ref2sink_bof.result
