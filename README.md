# PG_materialization

## Description
这是我在PG代码上的修改实验(github)。目的是实现在Hash node上收集其child node返回的数据并进行物化，如下图所示。

This code is modified based on PG. What I want to achieve is to collect all the return tuple from the child plan of Hash Join (specially, the Hash build node at PG's execution plan). The most modified code is at src/backend/executor/nodeHash.c, which is referenced by src/backend/utils/sort/tuplestore.c and src/backend/executor/nodeMaterial.c 
![image](https://user-images.githubusercontent.com/52020936/147085247-3b9ac023-3d4e-4b86-a58b-8a7ed0222ba5.png)

The functions that I added:
* ExecInitMaterialAtHashNode
* ExecMaterialAtHashNode
* ExecEndMaterialAtHashNode

## Usage
The code is based on PostgreSQL v13.0, you can replace the folder **src/backend/exectuor** directly, and then its supposed to work.

## Author
If you are user of Wechat, you may follow my public account "LearnDB"

![qrcode_for_gh_e6d9389929b9_258](https://user-images.githubusercontent.com/52020936/147086636-6c6a5d22-b2b2-4d60-baf0-06303cbbde40.jpg)
