# 运算与表达式

## 可用运算符

| Name | Operator | Simple |
| :---: | :--- | :--- |
| + - × ÷ | + - \* / |  |
| modulo | \# |  |
| brackets | \( \) |  |
| and | @& |  |
| or | @\| |  |
| xor | @^ |  |
| not | @~ |  |
| 连续求和 | b1+b2+···+b14 | sum\(1:14\) |
| 连续异或 | b1 xor b2 xor ··· xor b10 | sum\(1:10\) |
| 连续逻辑与 | b1 and b2 and ··· and b14 | and\(1:14\) |
| CRC8/CRC16 | [Know more](https://why.yuyeye.cc/post/how-to-calculate-crc8-and-crc16-in-mtools/) | [Know more](https://why.yuyeye.cc/post/how-to-calculate-crc8-and-crc16-in-mtools/) |

## 示例

| Rule | Expression |
| :--- | :--- |
| `b2 = b1` | `b2=b1` |
| `b4 = b2 + 0x1F` | `b4 = b2 + 31` |
| `b15 = b0 xor b1` | `b15 = b0 @^ b1` |
| `b2= not b0` | b2 = @~b0 |

* _请将十六进制数转化成十进制_
* _上下拖动表达式有改变计算顺序_
* _运算顺序为自上向下_

## 扩展用法

访问 [mXparser](http://mathparser.org/?s=Bitwise) 网站

