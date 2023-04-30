---
title: 个人项目 v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.17"

---

# 个人项目

> v1.0.0

Base URLs:

# shipping

## POST 创建托运人

POST /shippers

> Body 请求参数

```yaml
id: "1"
name: Paul
email: 374628@163.com
phone: "15707639231"

```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|object| 否 |none|
|» id|body|number| 是 |none|
|» name|body|string| 是 |none|
|» email|body|string| 是 |none|
|» phone|body|number| 是 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "data": {
    "id": 0,
    "name": "string",
    "email": "string",
    "phone": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» data|[Shipper](#schemashipper)|true|none||none|
|»» id|number|true|none||none|
|»» name|string|true|none||none|
|»» email|string|true|none||none|
|»» phone|number|true|none||none|

## GET 查询订单详情（追踪）

GET /order/{orderId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|orderId|path|number| 是 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "data": {
    "id": 0,
    "shipper_id": 0,
    "carrier_id": 0,
    "shipper_phone": 0,
    "carrier_phone": 0,
    "from_addr": "string",
    "dest_addr": "string",
    "createTime": "string",
    "finishTime": "string",
    "status": 0,
    "currentLocation": "string"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|记录不存在|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» data|[Order](#schemaorder)|true|none||none|
|»» id|number|true|none||none|
|»» shipper_id|number|true|none||none|
|»» carrier_id|number|true|none||none|
|»» shipper_phone|number|true|none||none|
|»» carrier_phone|number|true|none||none|
|»» from_addr|string|true|none||始发地|
|»» dest_addr|string|true|none||目的地|
|»» createTime|string|true|none||订单创建时间|
|»» finishTime|string|false|none||订单完成时间|
|»» status|integer|true|none||状态（0已创建/1运送中/2已完成）|
|»» currentLocation|string|false|none||当前位置|

状态码 **404**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|

## POST 创建订单

POST /order

> Body 请求参数

```yaml
id: 0
shipper_id: 0
shipper_name: string
shipper_phone: 0
carrier_id: 0
carrier_name: string
carrier_phone: 0
from_addr: string
dest_addr: string
createTime: string
status: 0

```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|object| 否 |none|
|» id|body|number| 是 |3501|
|» shipper_id|body|number| 是 |1|
|» shipper_name|body|string| 是 |Paul|
|» shipper_phone|body|number| 是 |15707639231|
|» carrier_id|body|number| 是 |23|
|» carrier_name|body|string| 是 |JD|
|» carrier_phone|body|number| 是 |1570839782|
|» from_addr|body|string| 是 |北京市海淀区|
|» dest_addr|body|string| 是 |广东省广州市|
|» createTime|body|string| 是 |20230430232201|
|» status|body|integer| 是 |0|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "data": {
    "id": 0,
    "shipper_id": 0,
    "carrier_id": 0,
    "shipper_phone": 0,
    "carrier_phone": 0,
    "from_addr": "string",
    "dest_addr": "string",
    "createTime": "string",
    "finishTime": "string",
    "status": 0,
    "currentLocation": "string"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» data|[Order](#schemaorder)|true|none||none|
|»» id|number|true|none||none|
|»» shipper_id|number|true|none||none|
|»» carrier_id|number|true|none||none|
|»» shipper_phone|number|true|none||none|
|»» carrier_phone|number|true|none||none|
|»» from_addr|string|true|none||始发地|
|»» dest_addr|string|true|none||目的地|
|»» createTime|string|true|none||订单创建时间|
|»» finishTime|string|false|none||订单完成时间|
|»» status|integer|true|none||状态（0已创建/1运送中/2已完成）|
|»» currentLocation|string|false|none||当前位置|

## GET 根据承运人查找订单列表

GET /order/findByCarrier

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|carrier_id|query|number| 是 |none|

> 返回示例

> 200 Response

```json
{
  "id": 0,
  "shipper_id": 0,
  "carrier_id": 0,
  "shipper_phone": 0,
  "carrier_phone": 0,
  "from_addr": "string",
  "dest_addr": "string",
  "createTime": "string",
  "finishTime": "string",
  "status": 0,
  "currentLocation": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|记录不存在|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» id|number|true|none||none|
|» shipper_id|number|true|none||none|
|» carrier_id|number|true|none||none|
|» shipper_phone|number|true|none||none|
|» carrier_phone|number|true|none||none|
|» from_addr|string|true|none||始发地|
|» dest_addr|string|true|none||目的地|
|» createTime|string|true|none||订单创建时间|
|» finishTime|string|false|none||订单完成时间|
|» status|integer|true|none||状态（0已创建/1运送中/2已完成）|
|» currentLocation|string|false|none||当前位置|

状态码 **404**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|

# 数据模型

<h2 id="tocS_Order">Order</h2>

<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "id": 0,
  "shipper_id": 0,
  "carrier_id": 0,
  "shipper_phone": 0,
  "carrier_phone": 0,
  "from_addr": "string",
  "dest_addr": "string",
  "createTime": "string",
  "finishTime": "string",
  "status": 0,
  "currentLocation": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|number|true|none||none|
|shipper_id|number|true|none||none|
|carrier_id|number|true|none||none|
|shipper_phone|number|true|none||none|
|carrier_phone|number|true|none||none|
|from_addr|string|true|none||始发地|
|dest_addr|string|true|none||目的地|
|createTime|string|true|none||订单创建时间|
|finishTime|string|false|none||订单完成时间|
|status|integer|true|none||状态（0已创建/1运送中/2已完成）|
|currentLocation|string|false|none||当前位置|

<h2 id="tocS_Shipper">Shipper</h2>

<a id="schemashipper"></a>
<a id="schema_Shipper"></a>
<a id="tocSshipper"></a>
<a id="tocsshipper"></a>

```json
{
  "id": 0,
  "name": "string",
  "email": "string",
  "phone": 0
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|id|number|true|none||none|
|name|string|true|none||none|
|email|string|true|none||none|
|phone|number|true|none||none|

