# PG_materialization

## Description
这是我在PG代码上的修改实验(github)。目的是实现在Hash node上收集其child node返回的数据并进行物化，如下图所示。

This code is modified based on PG. What I want to achieve is to collect all the return tuple from the child plan of Hash Join (specially, the Hash build node at PG's execution plan). The most modified code is at src/backend/executor/nodeHash.c, which is referenced by src/backend/utils/sort/tuplestore.c and src/backend/executor/nodeMaterial.c 
![image](https://user-images.githubusercontent.com/52020936/147085247-3b9ac023-3d4e-4b86-a58b-8a7ed0222ba5.png)

## Usage
The code is based on PostgreSQL v13.0, you can replace the folder backend directly, and then its supposed to work.
