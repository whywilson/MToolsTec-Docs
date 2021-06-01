# Algorithm & Expression

## Available Operator

| Name | Operator | Simple |
| :---: | :--- | :--- |
| + - × ÷ | + - \* / |  |
| modulo | \# |  |
| brackets | \( \) |  |
| and | @& |  |
| or | @\| |  |
| xor | @^ |  |
| not | @~ |  |
| Continuous summation | b1+b2+···+b14 | sum\(1:14\) |
| Continuous XOR | b1 xor b2 xor ··· xor b10 | sum\(1:10\) |
| Continuous logical AND | b1 and b2 and ··· and b14 | and\(1:14\) |
| CRC8/CRC16 | [Know more](https://why.yuyeye.cc/post/how-to-calculate-crc8-and-crc16-in-mtools/) | [Know more](https://why.yuyeye.cc/post/how-to-calculate-crc8-and-crc16-in-mtools/) |

## Example

| Rule | Expression |
| :--- | :--- |
| `b2 = b1` | `b2=b1` |
| `b4 = b2 + 0x1F` | `b4 = b2 + 31` |
| `b15 = b0 xor b1` | `b15 = b0 @^ b1` |
| `b2= not b0` | b2 = @~b0 |

* _Please convert the hexadecimal number to decimal_ 
* _Drag expression up/down to change the sequence_
* The calculation starts from the top to the end.

## Extended Usage

Visit [mXparser](http://mathparser.org/?s=Bitwise) WebSite

