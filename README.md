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
