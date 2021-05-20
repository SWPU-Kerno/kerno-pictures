# 数据库设计(初稿)

## 用户表
| 名      | 类型    | PK  | 注释         |
| ------- | ------- | --- | ------------ |
| user_id | integer | 1   | 用户唯一标识 |
| role    | tinyint |     | 用户权限id   |
| state   | tinyint |     | 状态         |
| name    | varchar |     | 用户名称     |
| pwd     | varchar |     | 用户密码     |
| sid     | varchar |     | 用户学号     |
| grand   | varchar |     | 用户年级     |

```ts
enum USER_ROLE{
    // 普通
    ORDINARY,
    // 管理员
    ADMIN
}

enum USER_STATE{
    // 正常
    NORMAL,
    // 注册中
    REGISTER,
    // 冻结
    FREEZE,
}
```

## 图片表
| 名            | 类型      | PK  | 注释         |
| ------------- | --------- | --- | ------------ |
| pic_id        | integer   | 1   | 图片唯一标识 |
| state         | tinyint   |     | 图片状态     |
| upload_time   | timestamp |     | 上传时间     |
| shooting_time | datetime  |     | 拍摄时间     |
| size          | integer   |     | 图片大小     |
| area_size     | varchar   |     | 图片尺寸     |
| pic_format    | varchar   |     | 图片格式     |
| name          | varchar   |     | 原名称       |
| link          | varchar   |     | 链接         |
| desc          | varchar   |     | 图片描述     |


```ts
enum PIC_STATE{
    // 公开
    PUBLIC,
    // 注册用户
    REGISTER,
    // 仅自己
    SELF
}
```

## 标签

| 名       | 类型    | PK  | 注释             |
| -------- | ------- | --- | ---------------- |
| label_id | integer | 1   | 图片标签唯一标识 |
| user_id  | integer |     | 创建用户         |
| name     | varchar |     | 标签名称         |

## 图片与标签关联

| 名         | 类型    | PK  | 注释       |
| ---------- | ------- | --- | ---------- |
| pic_id     | integer | 1   | 关联图片   |
| label_id   | integer |     | 关联标签   |
| user_id    | integer |     | 添加的用户 |
| label_name | varchar |     | 标签名称   |