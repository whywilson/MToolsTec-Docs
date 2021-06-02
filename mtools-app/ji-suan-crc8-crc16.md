# 计算CRC-8 / CRC-16

CRC - 循环冗余校验广泛用于数据传输。 根据 `wikipedia.org` 的描述，启用 CRC 的设备为要发送或存储的每个数据块计算一个短的、固定长度的二进制序列，称为校验值或 CRC，并将其附加到数据中，形成一个代码字。

`When a codeword is received or read, the device either compares its check value with one freshly calculated from the data block, or equivalently, performs a CRC on the whole codeword and compares the resulting check value with an expected residue constant.  
If the CRC values do not match, then the block contains a data error.`

`译文：当接收或读取代码字时，设备要么将其校验值与从数据块中新计算出的校验值进行比较，要么等效地对整个代码字执行 CRC，并将结果校验值与预期的剩余常数进行比较。 如果 CRC 值不匹配，则块包含数据错误。`

手动计算CRC值真的很难且浪费时间，因此我们在MTools中添加了CRC8 & CRC16算法。 这确实可以节省您通过一个表达式获取 CRC 值的时间。 

_注意：这是一个完整版的付费特性。_

## 字节变量

Mifare 1K 卡片的每一块中包含 16 个字节，可以使用`b0` `b1` `b2` ... `b14` `b15` 作为每一字节变量。

## CRC-8 校验

CRC-8的校验值只有一个字节，MTools支持的CRC-8算法如下：

| 算法 | 表达式 | 运算结果 |
| :---: | :--- | :---: |
| CRC-8 | crc8\(**0,1,5,8**\) |  `b0` `b1` `b5` `b8`的CRC-8校验值 |
| CRC-8/CDMA2000 | crc8cdma2000\(**0:14**\) | `b0` 到 `b14` 的CRC-8/CDMA2000校验值 |
|  CRC-8/DARC | crc8darc\(**0:14**\) | 参考上一条 |
| CRC-8/DVB-S2 | crc8dvs2\(**0:14**\) | 参考上一条 |
| CRC-8/EBU | crc8eu\(**0:14**\) | 参考上一条 |
| CRC-8/I-CODE | crc8icode\(**0:14**\) | 参考上一条 |
| CRC-8/ITU | crc8itu\(**0:14**\) | 参考上一条 |
| CRC-8/MAXIM | crc8maxim\(**0:14**\) | 参考上一条 |
| CRC-8/ROHC | crc8rohc\(**0:14**\) | 参考上一条 |
| CRC-8/WCDMA | crc8wcdma\(**0:14**\) | 参考上一条 |

## CRC-16 校验

CRC-16的校验值有两个字节。通过在表达式后加0或1，可以分布获得两个字节的值，MTools支持的CRC-16算法如下：

| 算法 | 表达式 0 | 表达式 1 | 两字节异或值 |
| :--- | :--- | :--- | :--- |
| CRC-16/CCITT-FALSE | crc16ccittfalse\(0:14\)0 | crc16ccittfalse\(0:14\)1 | crc16ccittfalse\(0:14\) |
| CRC-16/ARC | crc16arc\(0:14\)0 | crc16arc\(0:14\)1 | crc16arc\(0:14\) |
| CRC-16/AUG-CCITT | crc16augccitt\(0:14\)0 | crc16augccitt\(0:14\)1 | crc16augccitt\(0:14\) |
| CRC-16/BUYPASS | crc16buypass\(0:14\)0 | crc16buypass\(0:14\)1 | crc16buypass\(0:14\) |
| CRC-16/CDMA2000 | crc16cdma2000\(0:14\)0 | crc16cdma2000\(0:14\)1 | crc16cdma2000\(0:14\) |
| CRC-16/DDS-110 | crc16dds110\(0:14\)0 | crc16dds110\(0:14\)1 | crc16dds110\(0:14\) |
| CRC-16/DECT-R | crc16dectr\(0:14\)0 | crc16dectr\(0:14\)1 | crc16dectr\(0:14\) |
| CRC-16/DECT-X | crc16dectx\(0:14\)0 | crc16dectx\(0:14\)1 | crc16dectx\(0:14\) |
| CRC-16/DNP | crc16dnp\(0:14\)0 | crc16dnp\(0:14\)1 | crc16dnp\(0:14\) |
| CRC-16/EN-13757 | crc16en13757\(0:14\)0 | crc16en13757\(0:14\)1 | crc16en13757\(0:14\) |
| CRC-16/GENIBUS | crc16genibus\(0:14\)0 | crc16genibus\(0:14\)1 | crc16genibus\(0:14\) |
| CRC-16/MAXIM | crc16maxim\(0:14\)0 | crc16maxim\(0:14\)1 | crc16maxim\(0:14\) |
| CRC-16/MCRF4XX | crc16mcrf4xx\(0:14\)0 | crc16mcrf4xx\(0:14\)1 | crc16mcrf4xx\(0:14\) |
| CRC-16/RIELLO | crc16riello\(0:14\)0 | crc16riello\(0:14\)1 | crc16riello\(0:14\) |
| CRC-16/T10-DIF | crc16t10dif\(0:14\)0 | crc16t10dif\(0:14\)1 | crc16t10dif\(0:14\) |
| CRC-16/TELEDISK | crc16teledisk\(0:14\)0 | crc16teledisk\(0:14\)1 | crc16teledisk\(0:14\) |
| CRC-16/TMS37157 | crc16tms37157\(0:14\)0 | crc16tms37157\(0:14\)1 | crc16tms37157\(0:14\) |
| CRC-16/USB | crc16usb\(0:14\)0 | crc16usb\(0:14\)1 | crc16usb\(0:14\) |
| CRC-A | crc16a\(0:14\)0 | crc16a\(0:14\)1 | crc16a\(0:14\) |
| CRC-16/KERMIT | crc16kermit\(0:14\)0 | crc16kermit\(0:14\)1 | crc16kermit\(0:14\) |
| CRC-16/MODBUS | crc16modbus\(0:14\)0 | crc16modbus\(0:14\)1 | crc16modbus\(0:14\) |
| CRC-16/X-25 | crc16x25\(0:14\)0 | crc16x25\(0:14\)1 | crc16x25\(0:14\) |
| CRC-16/XMODEM | crc16xmodem\(0:14\)0 | crc16xmodem\(0:14\)1 | crc16xmodem\(0:14\) |

## 在嗅探中的应用

最后一个字节`b15`的计算方法为`CRC-8/MAXIM`，结果在一秒内可计算得出。

![](../.gitbook/assets/1559024659102.png)

