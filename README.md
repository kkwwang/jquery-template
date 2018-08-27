# jquery-template

#### 项目介绍
利用模板及正则解决js拼接html代码问题

<a target="_blank" href="http://www.210024.com/jquery-template/">演示地址</a>
|
<a target="_blank" href="https://gitee.com/wagk/jquery-template">bug提交地址</a>

#### 目的
插件主要目的：解决js拼接html代码


#### 参数说明

| 参数名 | 是否必须 | 描述 | 默认值 |
|:-----|:-----:|:-----|:-----|
| template | 必须 | 模板的jquery对象 | null |
| target | 可选 | 被刷新的dom的jquery对象 | null |
| data | 必须 | ajax请求后返回的数据，也就是需要替换到模板占位符的数据。 | null |
| nullText | 可选 | 当占位符对应的数据为null或不存在时的默认显示，可以是字符串，也可以是html | '' |
| prefix | 可选 | 占位符前缀 | '[' |
| suffix | 可选 | 占位符后缀 | ']' |


#### 使用说明

##### v1.0.1 版本仅提供两个功能

###### ajax请求后刷新部分dom

> 定制模板
```
<script type="text/html" id="userInfoTemp">
  <tr>
    <td>[id]</td>
    <td>[name]</td>
    <td>[sex]</td>
    <td>[age]</td>
  </tr>
</script>
```

> 调用模板
```
$.template({
  template: $("#userInfoTemp"),
  target: $("#userInfo"),
  data: _result.data,
  nullText: '<span style="color: red;">暂无</span>'
});
```

###### datatables等框架自定义列等场景

> 定制模板
```
<script type="text/html" id="actionsTemp">
  <div class="btns">
    <a href="javascript:alert('[id],[name],[age],[sex]')">查看</a>
    <a href="javascript:alert('[id],[name],[age],[sex]')">修改</a>
    <a href="javascript:alert('[id],[name],[age],[sex]')">删除</a>
  </div>
</script>
```
> 调用模板
```
// 给定需要插件执行的function：html
$.template("html", {
  template: $("#actionsTemp"),
  data: data,
});
```
