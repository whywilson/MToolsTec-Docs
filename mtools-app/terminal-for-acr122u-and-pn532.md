---
description: >-
  MTools App brings Terminal functions for ACR122U and PN532 via USB. Also
  bluetooth connection to PN532 with SPP module. You can run raw commands easily
  and debug PN532 or ACR122U with Android devices.
---

# Terminal for ACR122U & PN532

<figure><img src="../.gitbook/assets/image.png" alt="" width="365"><figcaption></figcaption></figure>

## How to use Terminal for ACR122U

The connection of ACR122U is USB. If you’re connecting it with your Android phone, an OTG adapter is necessary.

### Commands for ACR122U

#### Get Presented Tag info&#x20;

Before running on the command, the tag needs to be put on the reader. \
To get the UID of the connected PICC.&#x20;

```
> FF CA 00 00 04
< 
```

To get the ATS of the connected ISO 14443 A PICC.

```
> FF CA 01 00 04
< 
```

#### Load Mifare Key&#x20;

ACR122U allows loading 2 Mifare Keys(6 Bytes) in 2 locations.&#x20;



#### Verify Mifare Block



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

Check the checkbox of **Direct Transmit** and send the command of PN532. The command of PN532 is listed in the next section.
