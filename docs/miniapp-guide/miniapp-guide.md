---
title: 小程序平台操作指南
icon: lucide/smartphone
description: 智能公元小程序平台的账号管理、配网绑定、控制面板配置与运维指南
---

- 关注账号管理、配网绑定、控制面板配置与运维能力。
- 包含小程序的基础搭建、发布流程及日常使用操作。

## 小程序平台概述
- 功能：账号登录、设备列表、实时状态、控制面板、OTA、日志。
- 架构：前端小程序 + 智能公元平台 API。
- 平台地址：智能公元小程序系统 https://help.aimachip.com/docs/mini_program

---

## 第一部分：基础搭建及发布

### 1. 账号注册

打开网址[智能公元小程序系统](https://help.aimachip.com/docs/mini_program)，如果您还没有账号，请点击"立即注册"按钮进行注册。

如果您已注册了账号，请输入用户名和密码进入到系统，开始基本的搭建操作。

![账号注册页面](http://help.aimachip.com/uploads/mini_program/images/m_ddd08f9a2d99e73c40c15207be318bb9_r.png)

### 2. 小程序注册

**重要：授权小程序必须要企业主体的微信小程序账号。**

小程序注册有三种方式：快速注册、有公众号注册、无公众号注册。小程序必须完成认证和备案后，才能进行授权操作。

#### 2.1 快速注册

小程序平台支持快速注册小程序，通过智能公元平台快速创建小程序。

**操作步骤：**

1. **登录智能公元小程序系统**
    - 打开[智能公元小程序系统](https://help.aimachip.com/docs/mini_program)
    - 使用账号密码登录

    ![登录智能公元小程序系统](http://help.aimachip.com/uploads/mini_program/images/m_3e3c1ecb1a61775f1ff92dc5d151aee7_r.png)

2. **点击客户端>快速注册>立即注册**

    ![快速注册入口](http://help.aimachip.com/uploads/mini_program/images/m_e5f88bb6b2474b68826545ec3794e527_r.png)

3. **填写资料**
    - 填写企业信息、法人信息等必要资料

    ![填写资料](http://help.aimachip.com/uploads/mini_program/images/m_e4a79c1abcf8e168c867235a46ddedec_r.png)

4. **开始认证**
    - 4.1 法人的微信会收到创建小程序申请

        ![创建小程序申请](http://help.aimachip.com/uploads/mini_program/images/m_ede66d9815d1e18fb9858949de471159_r.png)

    - 4.2 点击开始认证

        ![开始认证](http://help.aimachip.com/uploads/mini_program/images/m_fd579e509d3590cf63a401393e894276_r.png)

    - 4.3 同意授权

        ![同意授权](http://help.aimachip.com/uploads/mini_program/images/m_fda037d97202f556c055b5effb1dc7e3_r.png)

    - 4.4 点击下一步

        ![点击下一步](http://help.aimachip.com/uploads/mini_program/images/m_5847fb5677a283023e9ccd4b3c9b30c6_r.png)
        ![下一步确认](http://help.aimachip.com/uploads/mini_program/images/m_8a6172241620411f7f4912b35f1581ff_r.png)

    - 4.5 在后台界面查看认证状态（如看不到变化，刷新页面）

        ![认证中状态](http://help.aimachip.com/uploads/mini_program/images/m_0164faa5b03495998eec1950cf12d4c2_r.png)

    - 4.6 验证成功

        ![验证成功](http://help.aimachip.com/uploads/mini_program/images/m_d2bd58be88e859c6a39982f60a7f0325_r.png)

    - 4.7 收到创建成功通知

        ![创建成功通知](http://help.aimachip.com/uploads/mini_program/images/m_0b64e960374e853b8be107b5a87ffadc_r.png)

5. **登录使用**
    - 前往手机微信里的"小程序助手"小程序设置登录邮箱和密码（重要）
    - 设置完成后前往[微信公众平台](https://mp.weixin.qq.com/)登录使用
    - 参考指引：<https://kf.qq.com/touch/sappfaq/200617VbQzaa200617aq67ru.html>
    - 最后设置小程序的名称、logo和服务类目

**注意事项：**

1. 注意保证主体信息与工商部门登记一致。如：广州和广州市；国家企业信用信息公示系统：<http://www.gsxt.gov.cn/index.html>
2. 确保微信号主人和微信支付绑定银行卡的主人姓名一致。需核实用户是否有改过名字，或者近期有做身份证升级（从15位身份证升级成18位身份证）。
3. 快速创建的小程序如何登录使用：可先前往"小程序助手"小程序设置登录邮箱和密码，设置完成后即可前往微信公众平台登录使用。

#### 2.2 有公众号注册

为方便公众号快捷接入小程序，并在各功能中使用小程序的服务，上线复用公众号资质注册小程序流程。快速注册认证小程序，无需重新提交主体材料、无需对公打款。

**条件：**

- 已认证的企业、媒体、政府、其他组织类型公众号

**限制：**

- 非个体户类型（企业、媒体、政府、其他组织类型）公众号一个月可以复用资质注册5个小程序
- 个体户一个月可以复用资质注册1个小程序

**开通入口：**

- 登录公众号 → 小程序 → 小程序管理 → 添加 → 快速注册并认证小程序

**相关规则：**

1. 复用资质创建的小程序默认与该公众号关联
2. 复用资质创建的小程序默认关联该公众号，不占一个月新增关联13个小程序的限制
3. 复用资质创建的小程序默认关联公众号，不下发模板消息，不默认出现在公众号资料页
4. 一个公众号若存在"待完成注册"的小程序，不可发起复用资质创建小程序
5. 一个公众号一个月内可复用资质注册小程序不多于5个（创建成功才占用）
6. 使用复用公众号资质注册小程序，将以本公众号的主体作为该小程序的开发者，可选择以本公众号运营者作为该小程序的管理员
7. 若选择了复用认证资质，则小程序完成注册后即是"已认证"状态

**创建流程：**

1. **登录公众号**
    - 登录公众号 → 小程序 → 小程序管理 → 添加 → 快速注册并认证小程序

    ![登录公众号](http://help.aimachip.com/uploads/mini_program/images/m_928b3a236de9e49f985c4a44f1826260_r.png)

2. **同意协议**

    ![同意协议](http://help.aimachip.com/uploads/mini_program/images/m_7463e6f73e326777cc7568386e510f7a_r.png)

3. **管理员扫码验证**

    ![管理员扫码验证](http://help.aimachip.com/uploads/mini_program/images/m_023617841e5b9c84e71d23db331d6bdc_r.png)

4. **勾选快速创建小程序的资质**
    - 复用微信认证资质不需要再次支付认证审核服务费，也不需要审核

    ![勾选资质](http://help.aimachip.com/uploads/mini_program/images/m_ea8ddc33954f73908def46ce970edba5_r.png)

5. **填写小程序帐号信息**
    - 需要一个未绑定个人微信或其他公众平台的邮箱

    ![填写账号信息](http://help.aimachip.com/uploads/mini_program/images/m_00c82d3281d0ec347be55d3eaf8a52c2_r.png)

6. **邮件激活小程序帐号**
    - 激活完成后即可使用邮箱帐号密码登录小程序

    ![邮件激活](http://help.aimachip.com/uploads/mini_program/images/m_c60bffa25bfcaab6eba253dfb3b27e03_r.png)

7. **绑定小程序管理员**
    - 注：绑定管理员，如果有在第四步有勾选复用运营者信息，最终以绑定管理员信息为准

    ![绑定管理员](http://help.aimachip.com/uploads/mini_program/images/m_c8a82c02f38781156234c2d538806534_r.png)

以上注册流程创建的小程序，不用再走小额打款验证主体。生成的帐号具有独立的邮箱帐号、密码，跟走正常注册流程注册的小程序具有一样的能力权限。

#### 2.3 无公众号注册

在微信公众平台官网首页直接注册小程序。

**注册流程：**

1. **注册方法**
    - 在[微信公众平台](https://mp.weixin.qq.com/)官网首页点击右上角的"立即注册"按钮

    ![立即注册](http://help.aimachip.com/uploads/mini_program/images/m_727770c72f9fa4844f8edf9bd2ee106e_r.png)

2. **选择注册的帐号类型**
    - 选择"小程序"，点击"查看类型区别"可查看不同类型帐号的区别和优势

    ![选择账号类型](http://help.aimachip.com/uploads/mini_program/images/m_5757459c54c854cedfd05132f872133e_r.png)

3. **填写邮箱和密码**
    - 请填写未注册过公众平台、开放平台、企业号、未绑定个人号的邮箱

    ![填写邮箱密码](http://help.aimachip.com/uploads/mini_program/images/m_f24372c31564c5ca118016ac18c3dab3_r.png)

4. **激活邮箱**
    - 登录邮箱，查收激活邮件，点击激活链接

    ![激活邮箱](http://help.aimachip.com/uploads/mini_program/images/m_07bd119a42625ee53eb32cefa05c8749_r.png)

5. **填写主体信息**
    - 点击激活链接后，继续下一步的注册流程
    - 选择主体类型，完善主体信息和管理员信息

    **选择主体类型：**

    ![选择主体类型](http://help.aimachip.com/uploads/mini_program/images/m_8fb50b942f691baeaad38861b70e0c0a_r.png)

    **主体类型说明：**

    ![主体类型说明](http://help.aimachip.com/uploads/mini_program/images/m_41d63b6fc5d3a2c8d47b2b3e37300a7f_r.png)

    **填写主体信息并选择验证方式：**

    - 企业类型帐号可选择两种主体验证方式：

        1. 需要用公司的对公账户向腾讯公司打款来验证主体身份，打款信息在提交主体信息后可以查看到。请根据页面提示，向指定的收款帐号汇入指定金额。温馨提示：请在10天内完成汇款，否则将注册失败。
        2. 通过微信认证验证主体身份，需支付300元认证费。认证通过前，小程序部分功能暂无法使用

    ![填写主体信息](http://help.aimachip.com/uploads/mini_program/images/m_889b2dfa242f5665f57124c4001107ee_r.png)

    **填写管理员信息：**

    ![填写管理员信息](http://help.aimachip.com/uploads/mini_program/images/m_de0b627a611aeeed0cfba7f887774314_r.png)

    **确认主体信息不可变更：**

    ![确认主体信息](http://help.aimachip.com/uploads/mini_program/images/m_d304b3583bd968d26a5ce991484f45e6_r.png)
    ![确认信息2](http://help.aimachip.com/uploads/mini_program/images/m_74ee75d1003d027bd3e6a6b8f33cb16a_r.png)

6. **微信认证**
    - 点击前往认证

    ![前往认证](http://help.aimachip.com/uploads/mini_program/images/m_09f2f2ba4e8b671818612944b0522de1_r.png)

    - 同意协议

    ![同意协议](http://help.aimachip.com/uploads/mini_program/images/m_b92443e9a5cf4712b2147e0025d6c338_r.png)

    - 填写资料

    ![填写资料1](http://help.aimachip.com/uploads/mini_program/images/m_2ed8c6a26175d16665d9c54729d47f88_r.png)
    ![填写资料2](http://help.aimachip.com/uploads/mini_program/images/m_ec5d38923aee1cfc3b957a9d966dab9e_r.png)

    - 填写发票

    ![填写发票](http://help.aimachip.com/uploads/mini_program/images/m_358587f08f80ab7e1ab5652c6948c4df_r.png)

    - 支付费用

    ![支付费用](http://help.aimachip.com/uploads/mini_program/images/m_6b4cfbf1c4b22511461cf250869a0dbc_r.png)

7. **认证审核**
    - 腾讯公司收到打款后，会及时将该帐号认证申请派发给第三方审核公司进行审核

    **温馨提示：**

    1. 腾讯公司收到打款后会在小信封通知对应审核公司名称及联系方式
    2. 审核过程中若有问题，审核公司会主动联系运营者

    ![认证审核](http://help.aimachip.com/uploads/mini_program/images/m_d753386ab1fed4ed9825d10f5d21add4_r.png)

### 2.4 小程序备案

小程序备案是微信小程序上线的必要步骤，需要在微信公众平台完成备案流程。

**备案指引：**

- 参考[小程序备案操作指引](https://developers.weixin.qq.com/miniprogram/product/record/record_guidelines.html)

**重要提示：**

- 小程序必须完成认证和备案后，才能进行授权操作
- 备案审核时间一般为1-5个工作日
- 备案通过后，小程序才能正式发布上线

### 3. 授权小程序

如果您已拥有微信小程序，点击**客户端 > 授权发布 > 一键授权**，将微信小程序授权给"智能公元"。

**前提条件：**

- 必须已完成小程序注册、认证和备案
- 必须为企业主体的微信小程序账号

![授权小程序页面](http://help.aimachip.com/uploads/mini_program/images/m_ebe9929c1befc9f67834e2b8357e6cf6_r.png)

### 4. 基本设置

#### 4.1 店铺设置

点击**店铺管理 > 店铺设置**，填写以下信息：

- 小程序名称
- 小程序简介
- 小程序logo

填写完成后点击提交。

![店铺设置页面](http://help.aimachip.com/uploads/mini_program/images/m_0d51dad41821da48440d9d47af2104e2_r.png)

#### 4.2 注册设置

点击**客户端 > 注册设置**，修改登录方式，一般默认即可。

![注册设置页面](http://help.aimachip.com/uploads/mini_program/images/m_721445a3fe2b29734d6fea1308b4921e_r.png)

#### 4.3 小程序设置

点击**客户端 > 小程序设置**，填写以下信息：

**必填项：**

- **小程序AppID**：从微信公众平台获取（参考"如何获取小程序AppID和AppSecret?"章节）
- **小程序AppSecret**：从微信公众平台获取

**支付功能（可选）：**

- 如果不需要支付功能，微信商户号MCHID和微信支付密钥APIKEY都填"1"即可
- 如果需要支付功能，请填写真实的商户号和密钥

![小程序设置页面](http://help.aimachip.com/uploads/mini_program/images/m_c04389ca395f12ad1681c607d2f6864b_r.png)

#### 4.4 短信设置

点击**设置 > 短信通知**，选择对应的短信平台进行设置。

短信主要用于：

- 发送验证码
- 订单通知

请根据自己的需要进行配置。

![短信设置页面](http://help.aimachip.com/uploads/mini_program/images/m_b69c95eaa6d67fd4e3d58589a97b9dc6_r.png)

#### 4.5 配送设置（可选）

点击**设置 > 配送设置 > 配送方式**，填写：

- 快递100Customer
- 快递100Key

默认是快递发货，请根据自己的需要进行配置。

![配送设置页面](http://help.aimachip.com/uploads/mini_program/images/m_0dc0e8fe8325691f2a844d8ce7f30604_r.png)

#### 4.6 运费模板设置（可选）

点击**设置 > 配送设置 > 运费模板**，点击"新增"创建运费模板，请根据自己的需要进行配置。

![运费模板设置](http://help.aimachip.com/uploads/mini_program/images/m_639768d65f189e819d47685e607a4a3a_r.png)

#### 4.7 物流公司设置（可选）

点击**设置 > 配送设置 > 物流公司**，请根据自己的需要进行配置。

![物流公司设置](http://help.aimachip.com/uploads/mini_program/images/m_638fb3544932e614eb2cc62277e0232f_r.png)

#### 4.8 发货地址和退货地址设置（可选）

点击**店铺管理 > 地址管理**，点击"新增"按钮，添加发货地址和退货地址，请根据自己的需要进行配置。

![地址管理页面](http://help.aimachip.com/uploads/mini_program/images/m_31a42e0eb0d96df0823a7bd4604e3d51_r.png)

#### 4.9 帮助中心设置（可选）

点击**内容管理 > 文件库管理 > 帮助中心**，点击"新增"按钮，填写帮助内容。

这部分内容将会在小程序**个人中心 > 帮助**中展示。请根据自己的需要进行配置。

![帮助中心设置](http://help.aimachip.com/uploads/mini_program/images/m_312558348c69b69b3bc598cb94f3a1b8_r.png)

### 5. 页面设计

**重要提示：如果已发布过小程序，后续修改页面后，不需要重新发布，只需要在微信小程序上刷新相关页面或者重新进入小程序即可看到效果。**

#### 5.1 页面设计

点击**页面管理 > 页面设计**，点击"新增"按钮，根据自己的需求进行页面修改。

**关键操作：**

- 如果想通过小程序控制设备，则必须要添加"设备组件"中的"设备列表"到页面中
- 点击底部"保存"按钮完成编辑

**重要：页面可以创建多个，但是必须要选择一个作为首页。**

![页面设计界面](http://help.aimachip.com/uploads/mini_program/images/m_b4a43f22c18fe34cd8bccdc3dea2fa0d_r.png)
![设备组件列表](http://help.aimachip.com/uploads/mini_program/images/m_597e2c87d68818f54b23f3d559f37ca2_r.png)

#### 5.2 分类模板

点击**页面管理 > 分类模板**，选择分类页样式，然后点击提交。

![分类模板设置](http://help.aimachip.com/uploads/mini_program/images/m_02838f3a63436fc404d1fc158d1830b0_r.png)

#### 5.3 底部导航

点击**页面管理 > 底部导航**，点击"新增"按钮创建导航栏。

**导航配置说明：**

- 初始会有四个默认导航按钮，可根据自己的需求进行修改
- 点击"选择链接"，为每个导航分配跳转链接页面
- 固定页面：首页（页面设计中标签为首页的页面）、分类页、购物车、个人中心
- 自定义页：通过填写对应的页面id（比如10001），就能将导航绑定到该页面

**重要：底部导航栏可以创建多个，但是必须要选择一个作为默认导航。**微信小程序里显示的底部导航栏为默认导航栏。

![底部导航设置](http://help.aimachip.com/uploads/mini_program/images/m_d40c1b148ef04e366d6b491bd189271a_r.png)

### 6. 发布小程序

#### 6.1 预览体验版

如果您还未进行微信授权小程序，请先授权小程序。

授权成功后，点击**客户端 > 微信小程序 > 授权发布**，点击"预览"按钮，扫描二维码即可查看体验版小程序。

![预览体验版](http://help.aimachip.com/uploads/mini_program/images/m_72e934dfb17703a97b4380d8e9b8f0f8_r.png)

#### 6.2 正式发布

体验版小程序确认无误后，点击"发布"按钮，在弹窗中点击确认发布。

**审核说明：**

- 审核一般1到5个工作日
- 审核成功后，在微信里会收到审核成功信息
- 平台授权发布页面里的状态会变成"已上线"

![发布小程序](http://help.aimachip.com/uploads/mini_program/images/m_dd5df3df44d0aa62ac36004cfe5605d7_r.png)

### 7. 如何获取小程序AppID和AppSecret

1. 前往[微信公众平台](https://mp.weixin.qq.com/)
2. 扫码登录
3. 点击左侧**开发 > 开发管理**，选择"开发设置"
4. 保存AppID和AppSecret
    - **AppID**：直接显示在页面上
    - **AppSecret**：需要通过点击右侧"重置"按钮获取

![获取AppID和AppSecret](http://help.aimachip.com/uploads/mini_program/images/m_6ab046f5f0c48312e6f78043514c22b0_r.png)

---

## 第二部分：设备管理

设备管理功能用于统一管理设备，提供查看设备的详细信息、控制设备状态、设置密码、固件管理等功能。

### 8. 设备列表

统一管理设备，提供查看设备的详细信息、控制设备状态、设置密码等功能。

![设备列表](http://help.aimachip.com/uploads/mini_program/images/m_5c9f9d841f209c25de5ecbb7e027d0e5_r.png)

#### 8.1 设备启用和禁用

点击按钮改变设备的启用状态。

- **启用**：设备可以被小程序正常使用
- **禁用**：设备无法被小程序控制

![设备启用禁用](http://help.aimachip.com/uploads/mini_program/images/m_bb0c94abfd60655ee4401311862fe692_r.png)

#### 8.2 密码设置

设备密码有两种模式：

- **后台管理密码**：用于后台管理设备
- **设备本地密码**：设备本地设置的密码

**设置后台管理密码：**

![设置密码1](http://help.aimachip.com/uploads/mini_program/images/m_070957d8eb5df18db0b900daf8ab8f7a_r.png)
![设置密码2](http://help.aimachip.com/uploads/mini_program/images/m_f4f10fc449db9f6cc19e0d475ff6a9f7_r.png)
![设置密码3](http://help.aimachip.com/uploads/mini_program/images/m_7c83b0e1fb8c791ac13a4707302b9a70_r.png)

**批量设置密码：**

- 勾选所有要设置的设备，点击"批量设置密码"按钮设置密码

![批量设置密码](http://help.aimachip.com/uploads/mini_program/images/m_bc5801e8c5db724af816c7b1a1f436e9_r.png)

#### 8.3 控件显示设置

针对单个设备，灵活调整控件。设置成功后立马生效。

![控件显示设置](http://help.aimachip.com/uploads/mini_program/images/m_f1627232193f416e19d493a15d474f04_r.png)

#### 8.4 实时日志

单击操作栏的实时日志，可查看设备运行中产生的数据日志，用于数据查看和问题排查。

![实时日志1](http://help.aimachip.com/uploads/mini_program/images/m_3d5f0bc7c9957959a7a36eb12a323ed8_r.png)
![实时日志2](http://help.aimachip.com/uploads/mini_program/images/m_6cfe2bc757d89ff7fe8c70ae1b122a45_r.png)

### 9. 固件管理

后台管理人员可以自行管理产品开发中上传的固件，通过上传的固件可以方便的对设备进行远程升级。

![固件管理](http://help.aimachip.com/uploads/mini_program/images/m_d4479ceb6aec8f8494247c618aac535d_r.png)

#### 9.1 固件上传

单击新增按钮，上传固件。

![固件上传1](http://help.aimachip.com/uploads/mini_program/images/m_442f455ab8038be3303562ab3b237cdf_r.png)
![固件上传2](http://help.aimachip.com/uploads/mini_program/images/m_857953928a77a59ec537ac561aba965e_r.png)

**固件上传说明：**

- 固件包建议从"智能公元平台上生成和下载"
- 解压固件包，找到后缀名为".bin.ota"的文件和"ota_cfg.json"文件
- 在步骤2导入"ota_cfg.json"文件
- 在步骤3导入后缀名为".bin.ota"的文件
- 完成后点击确定按钮

![固件上传3](http://help.aimachip.com/uploads/mini_program/images/m_b1bff7851d818ffd4b810b9461af8146_r.png)
![固件上传4](http://help.aimachip.com/uploads/mini_program/images/m_fb00d5a1a83ec3f12fbfaf273d1d0f4b_r.png)

**固件状态：**

- **上线**：表示该固件版本可以被使用，允许在固件升级中选择
- **下线**：表示该固件版本暂时无法使用

### 10. 固件OTA

当需要对批量的设备进行固件升级时，可以通过后台进行远程在线升级，无需烧录。

#### 10.1 新建任务

点击新建按钮，选择目标固件，配置以下参数：

- **目标固件**：升级的目标固件
- **待升级产品号**：用于选择本次需要升级的固件对应的产品号
- **待升级版本号**：用于选择本次需要升级的固件对应的版本号，包含等于和低于指定版本的版本
- **升级方式**：

    - **提醒升级**：用户在小程序/客户端收到升级提醒，可选择升级或不升级
    - **强制升级**：用户必须升级后才能继续使用
    - **检测升级**：用户选择对应设备的面板，主动更新
    - **静默升级**：设备定时检测，自动进行升级
- **升级超时时长**：用于规定OTA等待时间，超时判定为升级失败，可根据固件包大小和客户体验适当调整

![新建OTA任务1](http://help.aimachip.com/uploads/mini_program/images/m_451cea26602e36ca6e6c1e533ec878c8_r.png)
![新建OTA任务2](http://help.aimachip.com/uploads/mini_program/images/m_31e9bd95fd1fa38e6517674b356f46dd_r.png)

#### 10.2 发布任务

点击发布按钮，发布成功后，设备开始升级，用户在小程序端也能看到升级进度。

![发布OTA任务](http://help.aimachip.com/uploads/mini_program/images/m_73770b0327d724ad65e6f50b9d1235d9_r.png)

---

## 第三部分：日常使用操作

### 11. 账号注册与登录

1. 管理员在平台为运营人员开通账号与权限。
2. 打开小程序，使用手机号/企业账号登录。
3. 首次登录绑定企业或项目，启用二次验证。

![登录页面](http://help.aimachip.com/uploads/mini_program/images/m_3e3c1ecb1a61775f1ff92dc5d151aee7_r.png)

### 12. 设备配网与绑定

- 支持二维码、蓝牙辅助、AP 模式等多种配网方式。
- 步骤：添加设备 → 选择模组类型 → 复位设备 → 输入 Wi-Fi 信息 → 绑定成功。
- 常见问题：配网超时（检查信号/密码）、设备已被绑定（管理员解绑）。

![设备配网流程](http://help.aimachip.com/uploads/mini_program/images/m_5c9f9d841f209c25de5ecbb7e027d0e5_r.png)

### 13. 控制面板配置与自定义

- 在"面板编辑"模式拖拽控件（开关、滑块、数值显示）。
- 可绑定智能体/MCP 工具，实现语音控制与可视化联动。
- 支持主题、图标、布局预览。

![控制面板示例](http://help.aimachip.com/uploads/mini_program/images/m_bb0c94abfd60655ee4401311862fe692_r.png)

---

## 第四部分：常见问题与故障排查

### 14. 常见问题与故障排查

| 场景 | 可能原因 | 解决方案 |
| --- | --- | --- |
| 登录失败 | 权限不足/网络异常 | 重新授权、切换网络 |
| 控制面板无控件 | 未绑定模板 | 在控制台绑定后刷新 |
| 数据不刷新 | 长时间后台停留 | 下拉刷新或重新登录 |
| 配网超时 | 信号弱/密码错误 | 检查Wi-Fi信号强度、确认密码正确 |
| 设备已被绑定 | 设备已绑定其他账号 | 联系管理员解绑设备 |
| 小程序审核失败 | 信息不完整/违规内容 | 检查店铺设置、帮助中心内容 |
| 页面修改不生效 | 未刷新小程序 | 刷新相关页面或重新进入小程序 |
| 无法获取AppSecret | 未重置密钥 | 在微信公众平台点击"重置"按钮 |

---

## 第五部分：质检与维护

### 15. 质检与维护 / 变更记录

- 小程序发布新版本后，验证"登录→配网→控制→OTA"路径。
- 更新截图与操作说明，记录变更。
- 定期检查小程序功能是否正常，及时处理用户反馈。

| 日期 | 版本 | 改动 | 备注 |
| --- | --- | --- | --- |
| 2024-04-30 | v1.0 | 初始版本发布 | 包含基础搭建和发布流程 |
| 2024-11-28 | v1.1 | 图片完整性检查 | 确认70张图片完整 |

---

## 参考链接

- [智能公元小程序系统](https://help.aimachip.com/docs/mini_program)
- [基础搭建及发布](https://help.aimachip.com/docs/mini_program/mini_program-1e9ca38dt6dg3)
- [设备管理](https://help.aimachip.com/docs/mini_program/mini_program-1f5vp20d3egjb)
- [小程序注册](https://help.aimachip.com/docs/mini_program/mini_program-1e9c0aghs7jd2)
- [快速注册](https://help.aimachip.com/docs/mini_program/mini_program-1f609kcqsbhav)
- [有公众号注册](https://help.aimachip.com/docs/mini_program/mini_program-1f60as2lpkh27)
- [无公众号注册](https://help.aimachip.com/docs/mini_program/mini_program-1f60asdb1fqu6)
- [小程序备案](https://help.aimachip.com/docs/mini_program/mini_program-1finuobnf2uv3)
- [微信公众平台](https://mp.weixin.qq.com/)
- [小程序备案操作指引](https://developers.weixin.qq.com/miniprogram/product/record/record_guidelines.html)
