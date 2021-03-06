# API



### 返回格式

```json
{
    "code": 200,
    "data": {
    },
    "message": ""
}
```



## 搜索

### 简要描述

根据关键字搜索，适用筛选。核心功能

### 请求URL

`/api/search`

### 请求方式

`GET`

### 请求参数

| 参数名    | 必选 | 类型                                                        | 说明         | 默认值      |
| :-------- | :--- | :---------------------------------------------------------- | ------------ | ----------- |
| query     | 是   | string                                                      | 查询词       |             |
| size      | 否   | string ([Any size, Large, Medium, Small])                    | 图片大小，分界点为350K、150K     | 'Any size'  |
| color     | 否   | string ('#000000')                                          | 颜色，为空表示不筛选        |             |
| page      | 否   | int                                                         | 翻页         | 1           |
| num       | 否   | int                                                         | 一页数量     | 20          |

### 返回数据

| 参数   | 类型     | 描述         |
| :----- | :------- | :----------- |
| total  | int      | 总计多少结果 |
| page   | int      |              |
| num    | int      |              |
| images | [string] | image id     |



## 相似

### 简要描述

根据 id 获取某一图片的相似图片

### 请求URL

`/api/similar`

### 请求方式

`GET`

### 请求参数

| 参数名 | 必选 | 类型   | 说明     | 默认值 |
| :----- | :--- | :----- | -------- | ------ |
| image  | 是   | string | image id |        |
| num    | 否   | int    | 数量     | 20     |

### 返回数据

| 参数   | 类型     | 描述     |
| :----- | :------- | :------- |
| num    | int      |          |
| images | [string] | image id |



## 获取图片

### 简要描述

根据 id 获取图片

### 请求URL

`/api/image`

### 请求方式

`GET`

### 请求参数

| 参数名 | 必选 | 类型             | 说明         | 默认值 |
| :----- | :--- | :--------------- | ------------ | ------ |
| image  | 是   | string           | image id     |        |
| size   | 否   | string (100*100) | width*height | 原图   |

### 返回数据

直接放回图片
