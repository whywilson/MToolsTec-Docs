# How To Use Sniffer

Depending on the Firebase of MTools, only 15% of MTools users have used Sniffer functions of MTools. It's really an easy tool for comparison and analysis. In this article, I'll show the tutorial of how to use Sniffer in MTools.

## Why Need Sniffer

After getting the keys of a sector which contains valid data, we need to compare data in different amount. So I made the Sniffer in MTools to gather and compare data more easily.  
 The light pink and light-blue background show if the bytes change.  
 

![](https://why.yuyeye.cc/post-images/1574347906909.jpg)

## Where is Sniffer in MTools

![](https://why.yuyeye.cc/post-images/1574347023367.jpg)

1. After adding a card in List Fragment, you can add a sector in Detail Fragment.
2. Fill in the keyA and keyB on one sector depending on your needs.
3. Click the 3rd section.

## How To Use Sniffer

### Mark Money Bytes

![](https://why.yuyeye.cc/post-images/1574349436660.jpg)

### Mark Check Bytes

![](https://why.yuyeye.cc/post-images/1574349445281.jpg)

### Tips of Expression

```text
Operator 
   • + - × ÷ Modulo ➡ + - * / # 
   • XOR ➡ @^ ➡ xor 
   • NOT ➡ @～ ➡ not 
   • AND ➡ @& ➡ and 
   • OR ➡ @| ➡ or 
   • Signed left shift n ➡ @<<n 
   • Signed right shift n ➡ @>>n 
   • More 

Examples 
   • b2=b1 ➡ b2=b1 
   • b4=b2+0x1F ➡ b4=b2+31(decimal) 
   • b15=b0 xor b1 ➡ b15=b0 xor b1 
   • b2=not b0 ➡ b2=not b0 Note 
   • Convert constant to decimal 
   • Drag up/down to change the order of calculation
```

### After Expression added

![](https://why.yuyeye.cc/post-images/1574350100574.jpg)

## Conclusion <a id="conclusion"></a>

If there is no **Strikethrough** on check bytes, it means all expressions are correct.  
 Now you know another tip of MTools.

