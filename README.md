---
description: Guide book for MTools app.
---

# Help & Info \| MTools

## 1.Overview

MTools is a Material Design APP to easily read, write, analyze and charge `Mifare Classic` Tag. What you need firstly:

1. `Mifare 1K`Supported Device.  
   * Inner NFC
   * USB:  `ACR122U`   `PN532`
   * Bluetooth:  `PN532`
2. KeyA and keyB of the sector. 

**Please comply with local laws, only used for study and testing.**

## 2.YouTube Chanel

{% tabs %}
{% tab title="Mifare 1K Card" %}
{% embed url="https://youtu.be/hEwhJWAt3a8" caption="Hack Mifare 1K Card without ACR122U" %}
{% endtab %}

{% tab title="Magic Card" %}
{% embed url="https://youtu.be/AWc7gp8vUKw" caption="What\'s Magic Card and How to Clone" %}
{% endtab %}

{% tab title="Mi Band NFC" %}
{% embed url="https://youtu.be/1Bl-FFALNic" caption="MTools read/write/clone data on Mi Band 3 NFC" %}
{% endtab %}

{% tab title="ACR122U" %}
{% embed url="https://youtu.be/a7nUWIN7s-4" caption="Read card with ACR122U on Android phone" %}
{% endtab %}
{% endtabs %}





## 3. Lists

### 3.1 Add Card

Click the **+ floating button** will display `Add Card Dialog`, put the Mifare Classic Card close to the NFC antenna, then you can add a card to the APP.

### 3.2 Remove Card

Slide the item toward the right to remove the card.

### 3.3 Sort Card

Press and drag to sort cards.

### 3.4 Filter Card

Drag down the list to filter cards by name, UID, SAK, or DateTime.

### 3.5 Import \*.mto File

\*.mto file is the specific JSON file that includes tag information, keys, and rules.

### 3.6 Export File

Supports exporting to  5 types: 

* `*.mto` Includes card sectors, dumps, and rules.
* `card-list.csv` Includes card, id, name, SAK, and DateTime.
* `keys.txt` Includes all keys added.
* `sniffer.csv` Includes all sniffer records.
* `record.csv` Includes all charging records.

## 4. Details

![](.gitbook/assets/button_func.jpeg)

### 4.1 Add & Remove Sector

🆕Click the  **+** floating butto**n** and choose `Add 1 Sector`, select the sector number by sliding the picker, and enter 6 bytes \(12 characters\) valid key A or key B, click `Complete` to save.

◀Slide the item toward the right to remove the sector and keys.

### 4.2 Modify Key

Click the  **modify button**  will display the `Modify Key Dialog`, select new sector number by sliding the picker, and modify the 6 bytes \(12 digits or letters\) valid key A or key B, click `Complete`save new keys or sector.

### 4.3 Read Sector

After the card is close to the NFC antenna, click on the **read button** will read 4 blocks of data from the clicked sector, you can modify and write the new data.

### 4.4 Manage Rule

![](.gitbook/assets/mt-handle-block.jpg)

* Check on the checkbox for the block to handle.
* Click on **MARK** to mark selected blocks.
* Click on **COPY TO** to copy the rule to another card.

#### **4.4.1 Mark Money Byte**

![](.gitbook/assets/mark_money.jpeg)

Mark the byte, then verify the money is correct, and click Next.

#### **4.4.2 Mark Checked Byte**

![](.gitbook/assets/mark_check.jpeg)

Check the bytes that change and add expressions. Make sure that it's correct then click OK.

#### **4.4.2.1 Supported operations:**

> Basic: + - × ÷
>
> Advanced : \#
>
> Logical : xor not
>
> CRC8: crc8, crc8cdma2000, crc8darc, crc8dvbs2, crc8ebu, crc8icode, crc8itu, crc8maxim, crc8rohc, crc8wcdma
>
> CRC16: crc16ccittfalse, crc16arc, crc16buypass, crc16cdma2000, crc16dds110, crc16dectr, crc16dectx, crc16dnp, crc16en13757, crc16genibus, crc16maxim, crc16mcrf4xx, crc16riello, crc16t10dif, crc16teledisk, crc16tms37157, crc16usb, crca, crc16kermit, crc16modbus, crc16x25, crc16xmodem

[Know More &gt;&gt;](mtools-app/help-or-add-expression.md#example)

#### **4.4.2.2 Sort Expressions**

Press and drag to sort Expressions.

The calculation is from top to end.

### 4.5 Data Sniffer

![](.gitbook/assets/tips_sniffer.jpg)

Must add correct keys before. After marked, it can be compared with highlight data.  
Data Backups/Restore, Compare vertically, Rule Repository.

### 4.6 Sort Sector

Press and drag to sort sector.

### 4.8 Import Dump

Click the  **+** floating button, `Add Dump File` choose dump type then select file. The dump file type MTools support: 

{% tabs %}
{% tab title="mfd" %}
Mifare Dump is a 1K size file that is read by PN532 with the libnfc tools.
{% endtab %}

{% tab title="bin" %}
1K size file that is read from Mifare 1K card by Proxmark 3 devices.
{% endtab %}

{% tab title="mct" %}
Text type dump file from`Mifare Classic Tools` app.
{% endtab %}
{% endtabs %}

## 5. Read From Card

Click the  **+** floating button ****and choose `Read From Card`,  you can add more keys and try to read as much data as possible from the card, and then save it to a dump file.

### 5.1 Key List

Start with default keys and customed keys added by users

### 5.2 Start To Read

Try to read as much as possible data with all keys in Key List.

## 6. Charge

### 6.1 Set Quotas

Click **+** button to change to **=** as Quotas. 

### 6.2 Clear Record

Long press **the recharge record list**, then pop up the dialog will allow you to clear the recharge record or not.

### 6.3 Show Calculate Result

Long press the floating button to preview the data generated on **Rule**.

## 7.Dependency

Thanks to the friends for the contribution to the open-source community, regardless of rank.

* `ikarus23` [MifareClassicTool](https://github.com/ikarus23/MifareClassicTool)  
* `afollestad` [material-dialogs](https://github.com/afollestad/material-dialogs)  
* `markormesher` [android-fab](https://github.com/markormesher/android-fab)  
* `didikee` [AndroidDonate](https://github.com/didikee/AndroidDonate)  
* `Ice-Box` [Ice-Box](http://catchingnow.com)  
* `uccmawei` [FingerprintIdentify](https://github.com/uccmawei/FingerprintIdentify)

