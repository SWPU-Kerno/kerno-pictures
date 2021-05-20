# kerno-pictures
酷诺相册薄
## 技术方案
* [Web端](https://github.com/SWPU-Kerno/photo-album-web):Vue
* [服务端](https://github.com/SWPU-Kerno/photo-album-server):Node.js+Express
* 数据库:
  * MySQL：存储应用数据
  * Redis：状态维护

## [学习计划](./study/README.md)


## 需求
<details>
<summary>
第一期需求
</summary>

粗略的描述
### 用户模块
* 用户注册
* 管理员审核
* 用户登录
* 用户基本信息
  * 学号
  * 密码
  * 年级
  * 姓名
### 图片模块
* 上传（拖拽/多选/粘贴）
* 图片管理与查看
* 图片状态
  * 公开
  * 注册用户可看
  * 仅自己可看
* 打标签（每个图片可由图片管理员、图片上传者打上不同的标签）
* 图片基本信息
  * 上传时间
  * 图片拍摄时间
  * 大小
  * 尺寸信息
  * 格式
  * 原名称
  * 链接

</details>


### [数据库设计](./db/README.md)

### [接口设计](./api/README.md)