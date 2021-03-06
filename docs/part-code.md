This document is used for manufacturing and inventory part management. 

The pcb assembly factory (smd) requires all parts are labelled with a customer-defined, easy-to-use part code, instead the part number printed on the tap, bulk, tray, or part. And this document describes the rules assigning such code to a part.

本文档用于生产和库存物料管理。

贴片厂要求客户为每包装物料提供一个客户自定义的物料编码，用标签贴在物料包装上，便于生产时识别。本文档定义冲南使用的物料的编码规则。

# 冲南物料编码

冲南物料编码采用简化规则，仅阻容器件编码体现器件值，其他器件仅体现分类并严控设计中使用的器件种类。

电感仅限于用在电源和天线匹配电路上，编码不体现器件值。

# 前缀

* R - 电阻
* C - 电容
* L - 电感
* F - 磁珠
* D - 二极管
* LED - 发光二极管
* Q - 三极管，MOS管，包括对管
* XTAL - 晶体
* IC - 芯片或有源模块
* ANT - 天线
* SW - 开关
* CONN - 连接器

# 编码规则

## 电阻

仅使用R前缀的电阻默认为0402封装SMD器件；编码规则：

```
R[4-character code][J or F]-XXXX
```

4-character code使用R, K, M等表示小数点位置，如不足四位前面填0补成4位。

J表示5%精度，F表示1%精度，该编码与color code一致，需要其他精度可查询标准color code使用的字母。

例如：
|value|code|
|-|-|
|10k,5%|R010KJ-xxxx|
|49.9R,1%|R49R9F-xxxx|


## 电容

默认的电容规格为：

* 小于等于4.7u的电容为0402封装，6.3V电压
* 大于4.7u的电容为0603封装，6.3V电压

如果不同与默认规格，使用CA, CB，...，增加前缀定义，目前已定义：

* CA前缀默认为0805封装，10V电压

编码规则：

```
C[4-character code]-XXXX
```

特殊规格使用CA, CB...替换C。

4字符规则与电阻相同，使用P, N, U, M表示皮法，纳法，微法，毫法，例如：

* 22p - C022P-xxxx
* 0.1u - C00U1-xxxx

## 电感和磁珠

电感使用封装和值编码，例如L1008-02U2-0001, L0806-02U2-0001；封装为英制。

磁珠仅使用封装编码，例如F0402-0001。

## 二极管、三极管、MOS管、LED

仅使用封装编码，封装只认TO，SOT和SOD，非标的SC70之类勿使用。

例如：

- D523-0001 (SOD-523)
- ESD883-0001 (SOT-883)
- Q883-0001 (SOT-883)
- Q363-0001 (SOT-363)
- LED0402-0001 

## 晶体

晶体使用极少，仅使用封装编码，禁止使用非标封装晶体。

例如：
- XTAL3225-0001
- XTAL2016-0001

## 芯片与模块

芯片使用IC前缀，第二个`-`分隔的字段表示类型，目前有`CPU`,`POWER`, `DDR3`,`EMMC`,`WIRELESS`,`CRYPTO`等类型，非核心功能芯片类型请使用`MISC`。

例如：

- IC-CPU-0001
- IC-POWER-0001
- IC-DDR3-0001

## 天线、开关、连接器

均仅使用分类编码。连接器有二级分类。例如：

- ANT-0001
- SW-0001
- CONN-USB-0001


