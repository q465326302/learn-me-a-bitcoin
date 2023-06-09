# 魔术字节

比特币网络上的消息分隔符。

![Magic Bytes-1.png](img/Magic%20Bytes-1-svg.png)

**魔术字节**被用作在[比特币网络](../../../Beginners/How%20Bitcoin%20Works/1.Network/Network.md)中[节点](../../../Beginners/How%20Bitcoin%20Works/1.Network/Nodes/Nodes.md)之间识别不同消息的方式。

例如，如果你正在尝试使用自己的代码连接到一个节点，则摸发送到该节点的每个消息都应该以f9beb4d9开头，从该节点接收到的每个消息也将以相同的魔术字节开头。

## 魔术字节。
魔术字节长度为4个字节，根据所在的网络不同，它们将不同。
|网络	|魔术字节|
|---|---|
|Mainnet	|f9beb4d9|
|Testnet3	|0b110907|
|Regtest	|fabfb5da|

### 例子
这是我从Testnet3网络上一个节点收到的版本信息：
```
0b11090776657273696f6e000000000066000000c0094f817e1101000d000000000000004659775800000000000000000000000000000000000000000000ffff0000000000000d000000000000000000000000000000000000000000000000003d2324b2fc764108102f5361746f7368693a302e31332e312fab3d100001
```
这是一条tx消息:
```
0b110907747800000000000000000000e1000000db31994501000000018ad494471addef205294beb3b2673e2734a0c558b8dbc1334412e42b4a730b32010000006a473044022060c7048255d32a3c8014775d93e32339ed9f460c1f33770fab14444af2cdfb5f02204bd6020742b5deda36712c55f5110a2f4d9ea6c97e45a90bca39d134932c91b2012103b93183cf139818b023f79d6b9dc0c9b80276df9f188948e587db80c988337ec7ffffffff0280d1f008000000001976a9141f81f255c1df8d1b7665e7e7340b893ede2301a988acb8665b00000000001976a9149d28b845d29c1237e7273df9108f1597d4939e0688ac00000000
```
>魔术字节也用于在[blk * .dat](../../Blockchain/Blkdat/blkdat.md)文件中分隔块数据。

## 为什么使用魔术字节？

如果你连接到比特币节点，请将从中获取的消息视为连续的数据流。
![Magic Bytes-1.png](img/Magic%20Bytes-2.gif)
节点以字节流的形式接收数据。 f9beb4d9 可帮助你确定新消息何时开始。
https://github.com/in3rsha/php-simple-bitcoin-node

如果你试图读取这些数据，最好有一种可靠的方法来知道何时开始（和结束）一个新消息。**这就是为什么一组特定的“魔法字节”被用作“标记”，以便你始终可以识别新消息的开头。**

因此，实际上没有什么“魔术”关于魔术字节-它只是一种分段数据的方法。

## 为什么特别选择这些字节？
这些字节没有特定的含义，除了：

>消息起始字符串的设计目的在正常数据中不太可能出现。字符很少使用上ASCII码，不是有效的UTF-8，并且会产生一个大的32位整数，具有任何对齐方式。-[chainparams.cpp](https://github.com/bitcoin/bitcoin/blob/master/src/chainparams.cpp)

它们可能是不同的，但这只是4个字节，具有使比特币网络有魔法字节的属性。

## 资源
* https://en.bitcoin.it/wiki/Protocol_documentation#Message_structure
* https://en.wikipedia.org/wiki/Magic_number_(programming)