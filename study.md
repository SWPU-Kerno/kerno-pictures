# 学习计划

## 12-14
### 1. Node环境搭建
* [安装教程](https://www.runoob.com/nodejs/nodejs-install-setup.html)
* [下载地址](https://nodejs.org/zh-cn/download/)

安装完后再 终端(控制台) 中输入下列指令查看是否安装成功
```sh
node -v
```

### 2. NPM
* [NPM介绍](https://www.runoob.com/nodejs/nodejs-npm.html)

熟悉几个简单指令的使用

版本查看
```sh
npm -v
```

切换镜像源
```sh
# 查看当前源
npm config get registry

# 设置为淘宝源
npm config set registry https://registry.npm.taobao.org/
```

初始化工程
```sh
# 创建一个空目录
mkdir testDir

# 进入此目录
cd testDir

# 初始化npm配置
npm init -y
```

完成上述步骤后 可以在目录（testDir）中看到生成了一个 `package.json`文件

#### 安装依赖
```sh
# 指令格式
npm install $packageName

# 比如安装jQuery
npm install jquery

# 执行完成后会生成node_modules文件目录，里面就有我们刚刚安装了jquery
# 同时package.json 中的 dependencies 属性也会多一项jquery的版本描述
# 还会生成一个 package-lock.json ，对安装的依赖进行版本锁定

# 安装生产阶段的包
npm install jquery --save

# 安装开发阶段的包
npm install jquery --save-dev
```

#### 卸载依赖
```sh
# 卸载生产环境的包
npm uninstall $packageName --save

# 卸载开发环境的包
npm uninstall $packageName -dev
```

更多相关指令，请自己百度/Google探索