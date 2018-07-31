# Asynchronous_paging
tsl实现异步分页
#### 通过ajax将前端页码传入后台，后台写sql分页（rownum实现），把查到的结果转换成json数据传回给js，由js动态生成显示。
#### sql server分页
```
(* 分页查询
  select top num * //num为每页的行数
  from
  (
   select row_number() over(order by file_name) as rownumber,* from file_list
  ) A
  where rownumber >n  //m为第几页 n=m*num
*)
```
##### 注意字符串拼接用$符
##### 前端绑定动态事件一定要注意标签要事先存在才可绑定 如：$("#page").on('click','a',function () {  } //为a标签动态绑定事件 中a一定要事先存在，这样的话js代码要放在id为page的div后面

###### 使用$.parseJSON(response);来将返回的json数据转换成对象进行显示输出

