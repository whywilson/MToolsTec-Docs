# Mifare Classic Tool vs MTools

## Supported Card

* R - Read
* W - Write
* C - Clone

|                    | Mifare Classic Tool |    MTools   |
| :----------------: | :-----------------: | :---------: |
|  Mifare Classic 1K |        R / W        |    R / W    |
|  Mifare Classic 4K |        R / W        |    R / W    |
| 1st gen Magic Card |        R / W        |  R / W / C  |
| 2nd gen Magic Card |        R / W        |  R / W / C  |
|     UFUID Card     |        R / W        |  R / W / C  |
|  Mifare Ultralight |                     |  R / W / C  |
|        NTAG        |                     |  R / W / C  |
|         羊城通        |                     |      R      |
|     More Cards     |                     | Coming Soon |

## **External Device**

|                 |                                    Mifare Classic Tool                                   |                         MTools                        |
| :-------------: | :--------------------------------------------------------------------------------------: | :---------------------------------------------------: |
|     ACR122U     | <p>Compatible </p><p><code>• Rooted need</code></p><p><code>• Plugin require </code></p> | <p>USB Connection<br><code>Built-in driver</code></p> |
|      PN532      |                                        Not support                                       |                     USB Connection                    |
| PN532 Bluetooth |                                        Not Support                                       |                  Bluetooth Connection                 |

## **Card Clone**

The real cloning of the Mifare classic card must have a changeable UID.

| Magic Card Type | Mifare Classic Tool |                           MTools                          |
| :-------------: | :-----------------: | :-------------------------------------------------------: |
|       UID       |     Not Support     | <p>Support</p><p><code>Require External Device</code></p> |
|       CUID      |       Support       |                          Support                          |
|      UFUID      |     Not Support     | <p>Support</p><p><code>Require External Device</code></p> |

## Operation Features

| Magic Card Type |  Mifare Classic Tool |                        MTools                       |
| :-------------: | :------------------: | :-------------------------------------------------: |
|     Reading     |      All sectors     |        <p>All Sectors</p><p>Single Sector</p>       |
|     Writing     |    Dump to sectors   |    <p>Dump to sectors</p><p>Sector to sector</p>    |
|     Cloning     |    Only CUID card    |               All UID Changeable Card               |
|    Analyzing    |    Between 2 dumps   |                  Between 24 blocks                  |
|   Highlighting  | 1 Standard Structure | <p>5 built-in structure</p><p>User can add more</p> |
|   Calculating   |      Not Support     |                       mXparser                      |
|     Charging    |      Not Support     |                      One-click                      |

## Data Comparision

|     Mifare Classic Tool     |      MTools     |
| :-------------------------: | :-------------: |
| Between 2 blocks in 2 dumps | Among 24 blocks |

![](<../.gitbook/assets/MCT vs MTools Data Comparision.jpg>)

## Dump Type

|      | Mifare Classic Tool |  MTools |
| :--: | :-----------------: | :-----: |
| text |       Support       | Support |
|  mfd |       Support       | Support |
|  bin |       Support       | Support |

## **Import/Export Type**

|            |                       Mifare Classic Tool                      |                                                                               MTools                                                                              |
| :--------: | :------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| **Import** | <p><code>• Dump File</code></p><p><code>• Keys File</code></p> |                                   <p><code>• Dump File</code></p><p><code>• Keys File</code></p><p><code>• Card Rule</code></p>                                   |
| **Export** | <p><code>• Dump File</code></p><p><code>• Keys File</code></p> | <p><code>• Card Rule</code></p><p><code>• Card List</code></p><p><code>• Dump File</code></p><p><code>• Keys List</code></p><p><code>• Charging Record</code></p> |

## Bcc Calculator

| Mifare Classic Tool |     MTools     |
| :-----------------: | :------------: |
|   Inner Calculator  | Auto calculate |

## Access Condition De-/Encoder

| Mifare Classic Tool |    MTools   |
| :-----------------: | :---------: |
|   Inner Calculator  | Not Support |
