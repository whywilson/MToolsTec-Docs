---
description: >-
  MTools App brings Terminal functions for ACR122U and PN532 via USB. Also
  bluetooth connection to PN532 with SPP module. You can run raw commands easily
  and debug PN532 or ACR122U with Android devices.
---

# Terminal for ACR122U & PN532

<figure><img src="../.gitbook/assets/image.png" alt="" width="365"><figcaption><p>Entry of Terminal for ACR122U &#x26; PN532 in MTools</p></figcaption></figure>

## How to use Terminal for ACR122U

The connection of ACR122U is USB. If you’re connecting it with your Android phone, an OTG adapter is necessary.

### Commands for ACR122U

#### Get Presented Tag info&#x20;

Before running on the command, the tag needs to be put on the reader. \
To get the UID of the connected PICC.&#x20;

<pre><code>> FF CA 00 00 <a data-footnote-ref href="#user-content-fn-1">04</a>
&#x3C; <a data-footnote-ref href="#user-content-fn-2">11 22 33 44</a> <a data-footnote-ref href="#user-content-fn-3">90 00</a>
</code></pre>

To get the ATS of the connected ISO 14443 A PICC.

<pre><code>> FF CA 01 00 00
&#x3C; <a data-footnote-ref href="#user-content-fn-4">6A 81</a> 00
</code></pre>

#### Load Mifare Key&#x20;

ACR122U allows loading 2 Mifare Keys(6 Bytes) in 2 locations.&#x20;

<pre><code>> FF 82 00 <a data-footnote-ref href="#user-content-fn-5">00</a> <a data-footnote-ref href="#user-content-fn-6">06</a> <a data-footnote-ref href="#user-content-fn-7">FF FF FF FF FF FF</a>  //Load key FFFFFFFFFFFF to 00 location
&#x3C; 90 00
</code></pre>

#### Verify Mifare Block

```
> FF 88 01 00 00
< 6A 81 00
```

#### Read Mifare Block&#x20;

Once the sector is successfully authenticated, the commands to read or write the block can be executed with the problem.

1.  Read Mifare Classic Block (16 Bytes)

    ```
    > FF CA 01 00 04
    < 
    ```
2.  Read Mifare Ultralight Page (4 Bytes)

    ```
    > FF CA 01 00 04
    < 
    ```
3.  Read Mifare Ultralight 4 Pages (16 Bytes)

    ```
    > FF CA 01 00 04
    < 
    ```

#### Write Mifare Block&#x20;



#### Set Buzzer and LED



#### Direct Transmit to PN532

Check the checkbox of **Direct Transmit** and send the command of PN532. The command of PN532 is listed in [the next section](terminal-for-acr122u-and-pn532.md#terminal-for-pn532).

## Terminal for PN532

Coming soon.

[^1]: Full Length

[^2]: UID

[^3]: The operation completed successfully.

[^4]: Function not supported.

[^5]: 00h \~ 01h = Key Location.&#x20;

    The keys will disappear once the reader is power down.

[^6]: Key Length

[^7]: Mifare Key
