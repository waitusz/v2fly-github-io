# Observatory 连接观测

连接观测组件通过定时通过指定的出站连接建立连接来确定出站代理的状态。 (v4.38.0+)
连接观测组件的观测结果可以被其他组件使用，如负载均衡程序及API。

目前仅支持连接 `api.v2fly.org` 进行连接状态检测。

## ObservatoryObject

```json
{
  "subjectSelector":[
    "outbound"
  ]
}
```

> `subjectSelector`: \[string\]

一个字符串数组，其中每一个字符串将用于和出站协议标识的前缀匹配。在以下几个出站协议标识中：`[ "a", "ab", "c", "ba" ]`，`"selector": ["a"]` 将匹配到 `[ "a", "ab" ]`。

被匹配到的出站连接将被定时连接以确定是否可用。