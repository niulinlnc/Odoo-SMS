# Odoo-SMS
### odoo集成短信服务，集成国内腾讯云、阿里云
#### 实现通过手机验码登录odoo系统，前提是在系统用户中设置好用户的手机号码。也可通过手机验证码进行用户注册
### 适用odoo版本： 11、12 社区版和企业版

### 安装模块依赖(必装)： 

> pip install qcloudsms_py

> pip install aliyun-python-sdk-core

### 请自行购买和好配置相应的短信服务商（腾讯云、阿里云）

# 注意事项： 

### 对于腾讯云短信正文模板，目前系统支持参数，在腾讯云配置时一定要注意配置两个自定义内容**{1}{2}**
> 短信正文示例： 验证码：{1}，请于{2}分钟内填写。如非本人操作，请忽略本短信。
> {1}:表示验证码；  {2}表示有效时长
	
### 对于阿里云的配置模板本模块只允许传递一个参数：
> 短信正文示例： 验证码${code},如非本人操作，请忽略本短信！
> 阿里云只允许配置一个变量，即${code}：验证码


### 短信模板示例（其中变量部分必须一致）
> **腾讯云-验证码模板**："验证码：{1}，请于{2}分钟内填写。如非本人操作，请忽略本短信。"

> **腾讯云-修改密码通知**： "你好: 你的账户信息已发生改变，新的账户信息为：用户名：{1}，密码：{2}，请及时登录系统并进行修改！"

> **阿里云-发送验证码模板**： "验证码为：${code}，您正在试图使用验证码登录ERP系统，若非本人操作，请勿泄露。"

> **阿里云-发送修改密码通知模板**： "你好: 你的账户信息已发生改变，新的账户信息为：用户名：${name}，密码：${pwd}，请及时登录系统查看或进行修改！"