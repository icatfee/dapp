# CatFee dapp
 
本文档介绍 CatFee DApp 的功能、使用场景以及支持的钱包。CatFee 是一款面向 TRON 生态的能量服务 DApp，支持购买能量、自动为 TRC20 转账准备能量，以及通过资源代理参与能量共享。

 
# CatFee

CatFee is a non-custodial TRON energy service DApp.

## Features

- Buy TRON Energy
- Auto Prepare Energy for TRC20 Transfers
- Resource Delegation

## Wallet Compatibility

- Binance Wallet
- TronLink
- TokenPocket
- OKX Wallet
- Bitget Wallet
- SafePal
- Trust Wallet


## Binance Wallet

CatFee supports access through Binance Wallet's DApp browser and Web3 environment.

## Ecosystem Compatibility

CatFee is accessible through wallet browsers and Web3 environments, including **BNB Chain** compatible wallets.
 

## 基础信息

| 字段 | 建议填写 |
| --- | --- |
| DApp 名称 | TRON Energy |
| 中文名称 | 波场能量 |
| 分类 | Tools / Utilities / DeFi Tools / TRON Energy |
| 支持网络 | TRON Mainnet |
| DApp URL | https://dapp.catfee.io |
| 官网 | `<官网 URL>` |
| 联系邮箱 | service@catfee.io |
| Telegram| [`<官方社媒>`](https://t.me/CatFeeOfficial) |
| 推特X | https://x.com/catfeeio|

| 支持语言 | 中文、英文 |
| 是否托管资产 | 否 |
| 是否需要钱包签名 | 是，所有链上操作均由用户在钱包中确认 |

## 一句话介绍

中文：

> CatFee 是面向 TRON 用户的能量服务 DApp，支持购买能量、自动为 TRC20 转账购买能量，以及出售闲置资源获取收益。

English:

> CatFee is a TRON energy service DApp for buying energy, auto-preparing energy for TRC20 transfers, and monetizing idle resources.

## 简短介绍

中文：

> CatFee 帮助 TRON 用户更方便地使用能量服务。用户可以为指定地址购买能量，或在 TRC20 转账前由系统估算能量并引导完成购买。持有闲置资源的用户也可以通过资源代理参与项目，按规则获取 TRX 收益。

English:

> CatFee helps TRON users access energy services more easily. Users can buy energy for a target address, or let CatFee estimate and prepare the required energy before a TRC20 transfer. Users with idle resources can also delegate resources to participating projects and receive TRX rewards according to the project rules.

## 详细介绍

中文：

> CatFee 是一个专注于 TRON 能量使用场景的 DApp。对于普通用户，CatFee 提供手工购买能量和自动购买能量两种方式：手工模式适合用户已知道接收地址和能量数量的场景；自动模式适合 TRC20 转账场景，用户只需要填写 token、目标地址和金额，系统会估算所需能量、引导购买能量，并在能量到账后继续执行转账。
>
> 对于拥有闲置资源的用户，CatFee 提供卖能量入口。用户可以通过钱包确认资源代理操作，将可用资源代理给项目，并根据项目规则获得收益。CatFee 不托管用户私钥，不直接控制用户资产，所有签名和链上交易都需要用户在钱包中确认。

English:

> CatFee is a DApp focused on TRON energy usage. For users who need energy, CatFee provides both manual and automatic purchase flows. Manual purchase is suitable when the user already knows the receiver address and energy amount. Automatic purchase is designed for TRC20 transfers: the user enters the token, recipient, and amount; CatFee estimates the required energy, guides the user through the energy purchase, and lets the user continue the transfer after energy delegation is confirmed.
>
> For users with idle resources, CatFee provides a sell-energy entry. Users can confirm resource delegation through their wallet and delegate available resources to participating projects to receive rewards according to project rules. CatFee does not custody private keys or directly control user assets. All signatures and on-chain transactions are confirmed by the user in their wallet.

## 核心功能

### 买能量

- 为指定 TRON 地址购买能量。
- 支持地址校验和地址激活状态提示。
- 支持展示实时库存、单价、资源费用和应付 TRX。
- 用户钱包签名 TRX 支付交易，后端创建能量订单并执行代理。
- 前端展示订单状态、代理哈希和确认状态。

### 自动购买

- 用户填写 TRC20 合约、目标地址和金额。
- 系统查询 token 余额并估算本次转账所需能量。
- 购买能量数量按估算值向上取整到千位，最低不低于平台最小值。
- 能量订单代理确认后，用户继续执行 TRC20 转账。
- 适合 USDT、USDD 等稳定币转账场景。

### 卖能量

- 展示可参与的资源项目。
- 展示用户可代理资源、地址统计、收益和记录。
- 用户通过钱包确认资源代理交易。
- 收益规则由项目配置和后端订单结算决定。

## 安全和非托管说明

 
> CatFee is non-custodial. It never asks for or stores users' private keys or seed phrases. All wallet connections, signatures, TRX payments, resource delegations, and TRC20 transfers are confirmed by users inside their wallets. CatFee only receives signed transaction data or public on-chain data required to process orders and display status.

中文说明：

> CatFee 是非托管 DApp，不要求也不会保存用户私钥或助记词。所有钱包连接、签名、TRX 支付、资源代理和 TRC20 转账都由用户在钱包中确认。CatFee 只接收处理订单和展示状态所需的签名交易数据或公开链上数据。

## 签名和交易说明

 
- DApp 登录：用户签名消息，用于证明当前钱包地址归属。
- TRX 支付：用户签名 TRX 转账交易，用于支付能量订单。
- 资源代理：用户签名并广播资源代理交易。
- TRC20 转账：自动购买流程最后一步由用户签名并广播 TRC20 转账。
- 后期自动化：如果支持“签名后由后端广播”，后端会校验交易内容，并在能量到账后广播，不会修改已签名交易。

## 风险提示

- 不承诺固定收益。
- 不承诺所有 TRC20 转账都能成功。
- 不承诺能量估算与最终消耗完全一致。
- 用户应自行确认收款地址、token 合约、金额和钱包签名内容。
- 资源代理、TRX 支付和 TRC20 转账都是链上操作，提交后通常不可撤销。

 风险说明：

> Users are responsible for verifying transaction details before signing. CatFee provides energy estimation and order execution status, but it cannot guarantee the success of every on-chain transaction. Rewards from resource delegation depend on project rules and actual settlement.

## 隐私说明


> CatFee only uses wallet addresses, signed messages, signed transaction data, and public on-chain data required for login, order processing, and status display. CatFee does not collect private keys, seed phrases, or wallet passwords.

## 问答

### CatFee 是否托管用户资产？

否。CatFee 不保存私钥、助记词或钱包密码。所有签名和交易确认都发生在用户钱包中。

### 用户为什么需要签名？

签名用于两类场景：一是 DApp 登录，证明用户控制当前地址；二是链上操作，例如 TRX 支付、资源代理和 TRC20 转账。

### CatFee 是否会自动转走用户资产？

不会。当前版本的链上交易都需要用户在钱包中确认。后期如支持后端自动广播，也只会广播用户已经签名且后端校验通过的交易。

### 自动购买为什么需要估算能量？

TRC20 转账需要消耗发起地址的能量。自动购买会先估算本次转账需要多少能量，再引导用户购买能量，降低用户手动判断成本。

### 卖能量是否保证收益？

不保证固定收益。卖能量收益取决于项目规则、用户代理资源数量、链上确认和后端结算。

### 支持哪些钱包？

项目通过统一钱包适配层接入主流 TRON DApp 钱包。当前适配方向包括 TronLink、OKX Wallet、Bitget Wallet、TokenPocket、imToken、SafePal、Trust Wallet、Binance Wallet 等，实际支持范围以线上版本和测试结果为准。

 

 
## 表单字段模板

### DApp Name

```text
CatFee
```

### Category

```text
Tools / Utilities / TRON Energy
```

### Short Description

```text
Buy TRON energy, auto-prepare energy for TRC20 transfers, and monetize idle resources.
```

### Full Description

```text
CatFee is a non-custodial TRON energy service DApp. Users can buy energy for a target address, automatically estimate and prepare energy before TRC20 transfers, and delegate idle resources to participating projects to receive rewards according to project rules. All wallet connections, signatures, payments, resource delegations, and TRC20 transfers are confirmed by users inside their wallets. CatFee does not store private keys, seed phrases, or wallet passwords.
```

### Supported Chains

```text
TRON Mainnet
```

### Permissions / Signing Purpose

```text
CatFee requests wallet signatures only for DApp login, TRX payment transactions, resource delegation transactions, and user-confirmed TRC20 transfers. All signing requests are initiated by user actions and displayed in the user's wallet for confirmation.
```

### Security Statement

```text
CatFee is non-custodial and never asks for or stores private keys, seed phrases, or wallet passwords. All transactions require user confirmation in the connected wallet. Backend services validate submitted transaction data before processing orders.
```
 
