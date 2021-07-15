# 如何使用嗅探

Depending on the Firebase of MTools, only 15% of MTools users have used Sniffer functions of MTools. It's really an easy tool for comparison and analysis. In this article, I'll show the tutorial of how to use Sniffer in MTools.

## 为什么需要嗅探

在获取包含有效数据的扇区的密钥后，我们需要比较不同数量的数据。因此我们制作了嗅探功能以便更轻松地收集和比较数据。 浅粉色和浅蓝色背景显示字节是否发生变化。 

![](https://why.yuyeye.cc/post-images/1574347906909.jpg)

## 嗅探功能在哪里

![](https://why.yuyeye.cc/post-images/1574347023367.jpg)

1. 在列表页面添加卡片后，便可以在详情页面添加扇区。
2. 可根据需要填充密钥A和密钥B。
3. 点击第三个部分。

## 如何使用嗅探

### 标记数据位

![](https://why.yuyeye.cc/post-images/1574349436660.jpg)

### 标记校验位

![](https://why.yuyeye.cc/post-images/1574349445281.jpg)

### 表达式的使用

```text
运算符 
   • + - × ÷ 求余 ➡ + - * / # 
   • 异或 ➡ @^ ➡ xor 
   • 非 ➡ @～ ➡ not 
   • 与 ➡ @& ➡ and 
   • 或 ➡ @| ➡ or 
   • 左移n位 ➡ @<<n 
   • 右移n位 ➡ @>>n 

范例 
   • b2=b1 ➡ b2=b1 
   • b4=b2+0x1F ➡ b4=b2+31(十进制数) 
   • b15=b0 xor b1 ➡ b15=b0 xor b1 
   • b2=not b0 ➡ b2=not b0 Note 

 注意事项
   • 请将十六进制数转变为十进制数进行计算 
   • 上下拖送可以改变计算顺序
```

![](https://why.yuyeye.cc/post-images/1574350100574.jpg)

## 总结 <a id="conclusion"></a>

如果校验位的计算结果中没有删除线，意味着表达式运算结果与原数据匹配。

