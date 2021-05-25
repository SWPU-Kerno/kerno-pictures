## 用户

| 接口描述  | 请求方法 | 路径             | 分组 |
| --------- | -------- | ---------------- | ---- |
| 登录      | POST     | /user/login      | user |
| 注册      | POST     | /user/register   | user |
| 忘记密码  | PUT      | /user/password   | user |
| 查看权限  | GET      | /user/permission | user |
| 注销/删除 | DEL      | /user/people     | user |

------

## 超级管理员

| 接口描述     | 请求方法 | 路径          | 分组  |
| ------------ | -------- | ------------- | ----- |
| 获取用户列表 | GET      | /admin/list   | admin |
| 更改用户状态 | PUT      | /admin/status | admin |

------

## 图片

| 接口描述                                                 | 请求方法 | 路径                   | 分组           |
| -------------------------------------------------------- | -------- | ---------------------- | -------------- |
| 加载所有图片                                             | GET      | /pictures              | pictures       |
| 查看图片详细信息                                         | GET      | /pictures/pic          | pictures       |
| 上传图片(提交的信息包括状态、时间、大小等)               | POST     | /pictures/addpic       | pictures       |
| 删除图片                                                 | DEL      | /pictures/pic          | pictures       |
| 给图片加上标签                                           | POST     | /pictures/label/add    | pictures_label |
| 移除图片的标签                                           | POST     | /pictures/label/del    | pictures_label |
| 更改图片状态(图片状态在上传时应该设定好，所以只存在更改) | POST     | /pictures/state/update | pictures_state |

------

## 标签

| 接口描述 | 请求方法 | 路径          | 分组  |
| -------- | -------- | ------------- | ----- |
| 创建标签 | POST     | /label/add    | label |
| 更改标签 | POST     | /label/update | label |
| 删除标签 | DEL      | /label/del    | label |
| 显示标签 | GET      | /label/all    | label |

