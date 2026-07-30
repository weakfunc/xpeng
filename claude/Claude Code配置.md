[TOC]



# 终端Claude Code配置

| 步骤                                       | IMG                                                          | 备注                                                         |
| ------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 检查本机是否有Node.js环境和git             | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-25-37.png) | npm --version<br/>node --version<br/>git --version           |
| （若没有环境，则需先配置Node.js和git环境） | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-27-48.png) | win版本。安装过程选择一路next。可能的报错：<br />[查询npm版本号报错](#查询npm版本号报错) |
| 安装claude code                            | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-45-14.png) | powershell输入：npm install -g @anthropic-ai/claude-code     |
| 验证安装                                   | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-45-55.png) | claude --version                                             |
| 配置win环境变量                            | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-47-45.png) | 1. Win+R<br />2. 输入%userprofile%\.claude<br />可能的报错：<br />[Claude配置文件目录不存在](#Claude配置文件目录不存在) |
| 配置代理服务器                             | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-58-45.png) | ANTHROPIC_BASE_URL是代理中转站地址<br />ANTHROPIC_AUTH_TOKEN是中转站提供的API令牌 |
| 检查中转站地址和API令牌是否正确            | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_17-02-50.png) | 访问代理官网查询最新地址                                     |
| 访问claude                                 | ![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_17-06-02.png) |                                                              |



# APP端Claude配置



# 报错

## 查询npm版本号报错

![](C:\Users\XPENG\Desktop\document\claude\1f1aa284-ad96-4a70-bb2b-41772561ed21.png)

解决：

PowerShell 的“脚本执行策略”禁止运行 `.ps1` 文件。先输入npm.cmd --version看是否能查询到npm版本号。若能则输入：

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

永久修复当前用户的 PowerShell 策略。修复后关闭终端，重新查询npm版本号理论上应该正常。



## Claude配置文件目录不存在

![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-50-07.png)

解决：

按下Win+R，输入：

```
%userprofile%
```

在目录下新建：.claude文件夹。并在文件夹内新建settings.json文件。

![](C:\Users\XPENG\Desktop\document\claude\Snipaste_2026-07-20_16-51-31.png)

并将以下内容输入json文件：

```
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "xxx",
    "ANTHROPIC_BASE_URL": "https://apinebula.com"
  },
  "includeCoAuthoredBy": false
}
```
