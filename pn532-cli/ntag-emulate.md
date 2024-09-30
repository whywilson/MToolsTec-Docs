---
description: Use PN532 to Emulate NDEF Message
---

# NTAG Emulate

PN532 CLI supports TgInitAsTarget as the NTAG with NDEF Message such as website link, email, phone number and etc.

### How to connect PN532

```
hw connect
```

### How to emulate website link

```
ntag emulate --uri https://pn532kiler.com
```

### How to emulate email

```
ntag emulate --uri mailto:info@pn532killer.com
```

### Video

{% embed url="https://youtu.be/RY3yHRz2pBE" %}
PN532 Emulate NDEF
{% endembed %}
