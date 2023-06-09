# 区块哈希
区块头的哈希值。
![block-hash-1.png](img/block-hash-1%20(1).png)

一个**区块哈希**基本上是[区块链](../../../Beginners/How%20Bitcoin%20Works/2.Mining/1.Blockchain/Blockchain.md)中一个[块](../../../Beginners/How%20Bitcoin%20Works/2.Mining/2.Blocks/Blocks.md)的参考编号。

## 如何获得一个块哈希？
通过两次使用SHA256对[块头](../block-header/block-header.md)进行[哈希](../../Other/Hash%20Function/Hash%20Function.md)， 可以获得一个块哈希。

## 例子

这是*区块123,456*的序列化块头：
```
010000009500c43a25c624520b5100adf82cb9f9da72fd2447a496bc600b0000000000006cd862370395dedf1da2841ccda0fc489e3039de5f1ccddef0e834991a65600ea6c8cb4db3936a1ae3143991
```
![block-hash-2.png](img/block-hash-2.svg)
![block-hash-2.png](img/block-hash-2.svg)
(*交换字节序*)
```
0000000000002917ED80650C6174AAC8DFC46F5FE36480AAEF682FF6CD83C3CA
```

### 工具:
*哈希块头*

### 相关页面:
[挖矿](../../Mining/Mining.md)