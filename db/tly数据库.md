| 字段名称 | 数据类型 |     释义     |     示例     |
| :------: | :------: | :----------: | :----------: |
| user_id  | Integer  | 用户唯一标识 |      1       |
|   name   | varchar  |   用户名称   |     张三     |
|  number  | varchar  |   用户学号   | 201931061008 |
|  grade   |   year   |   用户年级   |     2019     |
|   pwd    | varchar  |   用户密码   |    123456    |



图片信息：

| 字段名称 | 数据类型 |     释义     |                      示例                       |
| :------: | :------: | :----------: | :---------------------------------------------: |
| photo_id | Integer  | 图片唯一标识 |                        1                        |
|   name   | varchar  |  图片原名称  |                      聚会                       |
| addtime  | datetime |   上传时间   |               2021-5-11 12:12:12                |
| taketime | datetime |   拍摄时间   |               2021-5-10 12:12:12                |
|   size   | varchar  |   图片大小   |                      105kb                      |
| sizeinfo | varchar  | 图片尺寸信息 |                    1024*768                     |
|  format  | varchar  |   图片格式   |                      .jpg                       |
|   url    | varchar  |   图片链接   |    https://699pic.com/tupian-500470844.html     |
|  status  |   int    |   图片状态   | 1(表示公开)，2（注册用户可看），3（仅自己可看） |
|  label   | varchar  |   图片标签   |                    团队聚会                     |

