# 公信宝区块链浏览器(GXChain Explorer)

公信宝区块链浏览器是构建在公信链(GXChain)上的一个查询工具,提供区块(Block)查询,交易(Transaction)查询和账户(Account)查询功能

> 任何一方可以无偿使用此浏览器或进行二次开发, 但请注明项目来源:Powered by GXB

## 功能
- [x] 区块同步
- [x] 区块查询
- [x] 账户查询
- [x] 交易查询
- [ ] 可视化（部分）
- [ ] 多语言（已添加中文、英文）

## 环境依赖

必要环境: Node 6+

建议系统: OSX、Linux

## Node环境安装

建议使用NVM([Node Version Manager](https://github.com/creationix/nvm))进行安装:

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
. ~/.nvm/nvm.sh
nvm install v6
nvm use v6
```

## 克隆项目

```
git clone https://github.com/gxchain/gxbox.git
```

## 依赖安装

调试模式依赖于babel-node, 在克隆的工程下执行以下命令安装依赖:


```
npm install -g babel-node
npm install
```

## 开发模式启动

```
npm start
```

## 生产环境启动

```
NODE_ENV=production node server-dist/index.js
```

或者使用pm2启动

```
NODE_ENV=production pm2 start server-dist/index.js --name gxb-explorer
```

## API说明

### 1. 根据区块高度获取区块信息

```
/api/block/:block_height
```

### 2. 根据tx_id获取交易信息

```
/api/transaction/:tx_id
```

### 3. 根据账户id或账户名获取账户信息

```
/api/account/:name_or_id
```

### 4. 根据账户id或账户名获取账户余额

```
/api/account_balance/:name_or_id
```

## 常见问题

### 1. 提示GC
区块太大可能导致内存不足, 可以修改BlocksyncTask.js中的sync_block_length,默认值为1000(每次同步1000个区块)
