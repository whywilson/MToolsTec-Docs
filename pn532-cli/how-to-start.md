# How to Start

### Hardware Requirement

* PN532 + USB Serial Chip such as CH340
* All-in-one PN532 board from MTools Tec

### Software Requirement

* Python 3.5+
* Download [PN532 Python](https://github.com/whywilson/pn532-python)

### Steps to emulate NDEF with PN532

1. Enter _script_ and install requirement.

```mipsasm
cd script
pip install -r requirements.txt
```

2. Connect PN532 to the device and run the cli

```vim
cd script
python pn532_cli_main.py
```

3. Connect PN532 in the cli

```arduino
hw connect
```
