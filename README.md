#接口(除了登录均为get)
## 0、`/api/login`
- 提交表单
```json
    {
      "username": "",
      "password": ""
    }
```
- 返回值(0为成功，1为失败。状态1时msg显示对应错误提示)
```json
{
    "msg":"登录成功",
    "status":0
}
```


## 1、`/api/get_data_list`
- 参数：无   
- 返回值：
```json
{
    "data_list": [
        "hour",
        "day"
    ]
}
```

## 2、 展示单个数据集`/api/show_data_set`
- 参数:数据集名称
```json
{
  "dataset_name": ""
}
```
- 返回值:为整个数据集。遍历整个Json，其中每组key为列名(json字符串)，value（json数组）为该列中的所有元素


## 3、 数据集参数 `/api/model_params`
- 参数:快速构建中的各个参数
```json
{
    "name": "",
    "model_type": "",
    "model_choose": [],
    "metrics": [],
    "search_params": ""
}
```
返回值:自动生成的代码内容(String)