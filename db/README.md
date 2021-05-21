# 数据库设计

## 用户表
| 名      | 类型    | PK  | 注释                        |
| ------- | ------- | --- | --------------------------- |
| user_id | integer | 1   | 唯一标识                    |
| role    | tinyint |     | 权限                        |
| state   | tinyint |     | 状态                        |
| name    | varchar |     | 姓名                        |
| pwd     | varchar |     | 密码                        |
| sid     | varchar |     | 学号                        |
| grand   | varchar |     | 年级                        |
| contact | varchar |     | 联系方式（QQ/wechat/phone） |

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
```sql
create table user
(
    user_id int auto_increment comment '唯一标识'
        primary key,
    role    tinyint default 0 not null comment '权限',
    state   tinyint default 1 not null comment '状态',
    name    varchar(256)      not null comment '姓名',
    pwd     varchar(256)      not null comment '密码',
    sid     varchar(256)      not null comment '学号',
    grand   varchar(256)      not null comment '年级',
    contact varchar(256)      null comment '联系方式'
);
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
| type          | varchar   |     | 图片格式     |
| origin_name   | varchar   |     | 原名称       |
| link_path     | varchar   |     | 资源路径     |
| des           | varchar   |     | 图片描述     |


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
```sql
create table picture
(
    pic_id        int auto_increment
        primary key,
    state         tinyint   default 1                 not null comment '状态',
    upload_time   timestamp default CURRENT_TIMESTAMP not null comment '上传时间',
    shooting_time timestamp                           null comment '拍摄时间',
    size          int                                 not null comment '图片大小',
    area_size     varchar(256)                        not null comment '尺寸信息',
    type          varchar(256)                        not null comment '图片格式',
    origin_name   varchar(256)                        null comment '图片名称',
    link_path     varchar(1024)                       not null comment '资源路径',
    des           varchar(1024)                       null comment '图片描述'
)
    comment '图片';
```
## 标签

| 名       | 类型    | PK  | 注释             |
| -------- | ------- | --- | ---------------- |
| label_id | integer | 1   | 图片标签唯一标识 |
| user_id  | integer |     | 创建用户         |
| name     | varchar |     | 标签名称         |

```sql
create table label
(
    label_id int auto_increment comment '唯一标识'
        primary key,
    user_id  int          not null comment '创建人员',
    name     varchar(256) not null comment '标签名称'
)
    comment '标签';

```
## 图片与标签关联

| 名         | 类型    | PK  | 注释       |
| ---------- | ------- | --- | ---------- |
| rel_id     | integer | 1   | 唯一标识   |
| pic_id     | integer |     | 关联图片   |
| label_id   | integer |     | 关联标签   |
| user_id    | integer |     | 添加的用户 |
| label_name | varchar |     | 标签名称   |

```sql
create table label_pic_concat
(
    rel_id     int auto_increment comment '唯一标识'
        primary key,
    pic_id     int          not null comment '关联的图片',
    label_id   int          not null comment '关联的标签',
    user_id    int          not null comment '创建关系的用户',
    label_name varchar(256) not null comment '标签名称'
);
```