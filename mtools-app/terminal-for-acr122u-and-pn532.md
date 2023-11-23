---
description: >-
  MTools App brings Terminal functions for ACR122U and PN532 via USB. Also
  bluetooth connection to PN532 with SPP module. You can run raw commands easily
  and debug PN532 or ACR122U with Android devices.
---

# Terminal for ACR122U & PN532

<figure><img src="../.gitbook/assets/image.png" alt="" width="365"><figcaption><p>Entry of Terminal for ACR122U &#x26; PN532 in MTools</p></figcaption></figure>

## Terminal for ACR122U

The connection of ACR122U is USB. If you’re connecting it with your Android phone, an OTG adapter is necessary.

### Get Presented Tag info&#x20;

Before running on the command, the tag needs to be put on the reader. \
To get the UID of the connected PICC.&#x20;

<pre><code>> FF CA 00 00 <a data-footnote-ref href="#user-content-fn-1">04</a>
&#x3C; <a data-footnote-ref href="#user-content-fn-2">11 22 33 44</a> <a data-footnote-ref href="#user-content-fn-3">90 00</a>
</code></pre>

To get the ATS of the connected ISO 14443 A PICC.

<pre><code>> FF CA 01 00 00
&#x3C; <a data-footnote-ref href="#user-content-fn-4">6A 81</a> 00
</code></pre>

### Load Mifare Key&#x20;

ACR122U allows loading 2 Mifare Keys(6 Bytes) in 2 locations.&#x20;

<pre><code>> FF 82 00 <a data-footnote-ref href="#user-content-fn-5">00</a> <a data-footnote-ref href="#user-content-fn-6">06</a> <a data-footnote-ref href="#user-content-fn-7">FF FF FF FF FF FF</a>  //Load key FFFFFFFFFFFF to 00 location
&#x3C; 90 00
</code></pre>

### Verify Mifare Block

<pre><code>> FF 86 00 00 05 01 00 <a data-footnote-ref href="#user-content-fn-8">04</a> <a data-footnote-ref href="#user-content-fn-9">60</a> <a data-footnote-ref href="#user-content-fn-10">00</a>
&#x3C; 90 00
</code></pre>

_<mark style="color:blue;">Note: The MIFARE Classic 1K Card, has a total of 16 sectors and each sector consists of 4 consecutive blocks.</mark>_ \
_<mark style="color:blue;">E.g. Sector 00h consists of Blocks {00h, 01h, 02h and 03h};</mark>_ \
_<mark style="color:blue;">Sector 01h consists of Blocks {04h, 05h, 06h and 07h};</mark>_ \
_<mark style="color:blue;">the last sector 0F consists of Blocks {3Ch, 3Dh, 3Eh and 3Fh}.</mark>_ \
_<mark style="color:blue;">Once the authentication is done successfully, there is no need to authenticate again if the blocks to be accessed belong to the same sector.</mark>_ \
_<mark style="color:blue;">Please refer to the MIFARE Classic 1K/4K specification for more details.</mark>_

Note: **MIFARE Ultralight** does not need to do any authentication. The memory is free to access.

### Read Mifare Block&#x20;

Once the sector is successfully authenticated, the commands to read or write the block can be executed with the problem.

1.  Read Mifare Classic Block (16 Bytes)

    <pre><code>> FF B0 00 <a data-footnote-ref href="#user-content-fn-11">04</a> <a data-footnote-ref href="#user-content-fn-12">10</a>
    &#x3C; 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 90 00
    </code></pre>
2.  Read Mifare Ultralight Page (4 Bytes)

    <pre><code>> FF B0 00 <a data-footnote-ref href="#user-content-fn-13">04</a> <a data-footnote-ref href="#user-content-fn-14">04</a>
    &#x3C; 00 01 02 03 90 00
    </code></pre>
3.  Read Mifare Ultralight 4 Pages (16 Bytes)

    <pre><code>> FF B0 00 <a data-footnote-ref href="#user-content-fn-15">04</a> <a data-footnote-ref href="#user-content-fn-16">10</a>
    &#x3C; 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 90 00
    </code></pre>

### Write Mifare Block&#x20;

1.  Write Mifare Classic Block

    <pre><code>> FF D6 00 <a data-footnote-ref href="#user-content-fn-17">04</a> <a data-footnote-ref href="#user-content-fn-18">10</a> <a data-footnote-ref href="#user-content-fn-19">00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F</a>
    &#x3C; 90 00
    </code></pre>
2.  Write Mifare Ultralight Page

    <pre><code>> FF D6 00 <a data-footnote-ref href="#user-content-fn-20">04</a> <a data-footnote-ref href="#user-content-fn-21">04</a> <a data-footnote-ref href="#user-content-fn-22">00 01 02 03</a>
    &#x3C; 90 00
    </code></pre>

### Set Buzzer and LED

The bi-color LED and Buzzer all can be configured with commands. This command makes ACR122U much more cool and flexible to use.

<table><thead><tr><th align="center">Class</th><th width="122" align="center">INS</th><th align="center">P1</th><th width="160" align="center">P2</th><th width="79" align="center">Lc</th><th align="center">Data In(4 B)</th></tr></thead><tbody><tr><td align="center">FF</td><td align="center">00</td><td align="center">01</td><td align="center"><p>LED </p><p>State Control (Bit 7 --- Bit 0)</p></td><td align="center">04</td><td align="center">Blinking Duration Control</td></tr></tbody></table>

#### **LED State Control**

Bi-Color LED and Buzzer Control Format (1 byte)

<table><thead><tr><th width="104">CMD</th><th>Item</th><th>Description</th></tr></thead><tbody><tr><td>Bit 0</td><td>Final State : Red LED</td><td>1 = On ; 0 = Off</td></tr><tr><td>Bit 1</td><td>Final State : Green LED</td><td>1 = On ; 0 = Off</td></tr><tr><td>Bit 2</td><td>State Mask : Red LED</td><td>1 = Update the State<br>0 = No change</td></tr><tr><td>Bit 3</td><td>State Mask : Green LED</td><td>1 = Update the State<br>0 = No change</td></tr><tr><td>Bit 4</td><td>Initial Blinking State : Red LED</td><td>1 = On ; 0 = Off</td></tr><tr><td>Bit 5</td><td>Initial Blinking State : Green LED</td><td>1 = On ; 0 = Off</td></tr><tr><td>Bit 6</td><td>Blinking Mask : Red LED</td><td>1 = Blink<br>0 = Not Blink</td></tr><tr><td>Bit 7</td><td>Blinking Mask : Green LED</td><td>1 = Blink<br>0 = Not Blink</td></tr></tbody></table>

#### **Blinking Duration Control**

Bi-Color LED Blinking Duration Control Format (4 Bytes)

| Byte 0                                                            | Byte 1                                                           | Byte 2                         | Byte 3         |
| ----------------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------ | -------------- |
| <p>T1 Duration<br>Initial Blinking State<br>( Unit = 100 ms )</p> | <p>T2 Duration<br>Toggle Blinking State<br>( Unit = 100 ms )</p> | <p>Number of<br>repetition</p> | Link to Buzzer |

#### **Byte 3 Options**

Link to the Buzzer and control the buzzer state during the LED Blinking.&#x20;

```
00h: The buzzer will not turn on 
01h: The buzzer will turn on during the T1 Duration 
02h: The buzzer will turn on during the T2 Duration 
03h: The buzzer will turn on during the T1 and T2 Duration.
```

#### Response

<pre><code> &#x3C; 90 <a data-footnote-ref href="#user-content-fn-23">00</a>
 &#x3C; 63 00
</code></pre>

#### **Buzzer and LED Notes**

```
1. LED Blinking will take effect only if the corresponding LED Blinking Mask is enabled and the 
number of repetitions is greater than zero. 
2. The term Initial Blinking State means that the LED of the chosen color will either be turned 
ON or OFF during the first blink in the duty cycle. For example, if the Initial Blinking State is 
turned ON for the Green LED and OFF for the Red LED, then the blinking will start with Green, 
followed by Red, and so on. 
3. The change in LED State will take effect only if the corresponding LED State Mask is enabled.
4. If controlled at the same time, the LED State operation will be performed after the LED 
The blinking operation has been completed.
5. Under Blinking Duration Control, Both T1 and T2 duration parameters are used for controlling 
the duty cycle of LED blinking and Buzzer Turn-On duration. For example, if T1=1 and T2=1, 
the duty cycle = 50%. #Duty Cycle = T1/(T1 + T2).
6. To control the buzzer only, set the P2 “LED State Control” to 00.
7. To make the buzzer operate, the “number of repetitions” must be greater than zero.
8. To control the LED only, set the parameter “Link to Buzzer” to 00.

```

### Direct Transmit to PN532

This is the payload to be sent to the tag or reader with a specific command ahead.

<pre><code> > FF 00 00 00 <a data-footnote-ref href="#user-content-fn-24">DataLength</a> <a data-footnote-ref href="#user-content-fn-25">[Playload]</a>
 &#x3C; [ResponseData] 90 00
</code></pre>

Check the checkbox of **Direct Transmit** and send the command of PN532. The command of PN532 is listed in [the next section](terminal-for-acr122u-and-pn532.md#terminal-for-pn532).

## Terminal for PN532

Coming soon

[^1]: Full Length

[^2]: UID

[^3]: The operation completed successfully.

[^4]: Function not supported.

[^5]: 00h \~ 01h = Key Location.&#x20;

    The keys will disappear once the reader is power down.

[^6]: Key Length

[^7]: Mifare Key

[^8]: Block 04

[^9]: 60h = Key is used as a TYPE A key for authentication. \
    61h = Key is used as a TYPE B key for authentication.

[^10]: 00h \~ 01h = Key Location.

[^11]: Block 04

[^12]: Number of Bytes to Read

[^13]: Page 04

[^14]: Page byte count

[^15]: Start from Page 04

[^16]: Page date length, 10h is 16 bytes, which means page 4, 5, 6 and 7 will be read

[^17]: Block 04

[^18]: Number of Bytes to write

[^19]: Block data to write

[^20]: Page Index

[^21]: Data length

[^22]: Page data to write

[^23]: Current LED Status\
    000000<mark style="color:green;">**0**</mark><mark style="color:red;">**0**</mark>

    &#x20;               <mark style="color:red;">bit 0 - current Red LED</mark>

    &#x20;             <mark style="color:green;">bit 1 - current Green LED</mark>

[^24]: 1 byte. Number of bytes to send Maximum 255 bytes

[^25]: Data Bytes
