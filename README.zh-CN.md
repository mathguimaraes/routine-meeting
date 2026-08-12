<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**会议总会发生，记笔记不该是你的活儿。**

[官网](https://mathguimaraes.github.io/routine-meeting/zh-CN/) · [下载 macOS 版](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

[![en](https://img.shields.io/badge/lang-en-red.svg)](README.md)
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](README.es.md)
[![pt--br](https://img.shields.io/badge/lang-pt--br-green.svg)](README.pt-BR.md)
[![ja](https://img.shields.io/badge/lang-ja-blue.svg)](README.ja.md)
[![de](https://img.shields.io/badge/lang-de-orange.svg)](README.de.md)
[![fr](https://img.shields.io/badge/lang-fr-lightgrey.svg)](README.fr.md)
[![ko](https://img.shields.io/badge/lang-ko-blueviolet.svg)](README.ko.md)
[![zh--cn](https://img.shields.io/badge/lang-zh--cn-critical.svg)](README.zh-CN.md)

</div>

---

## 问题所在

你加入一通电话，一旦聊到关键内容，就得做出选择:专心听,还是赶紧记下来。会议刚开始那几句话,你可能正忙着找笔记软件而错过了。忘记按下录制键。到了周五,六场会议里定下的决定和待办事项,全都只留在你的记忆里。

大多数录音工具不但没帮上忙,反而添乱——你得自己记得按开始键,它们把原始音频上传到某个服务器,而且一半的工具连你和别人的声音都分不清。

## Routine Meeting 能做什么

Routine Meeting 安静地待在你的菜单栏,不用你开口,它就把一切都处理好了:

- **察觉到你在开会,自动开始录音——在*任何*应用里都行。** 它不是那种只对接 Zoom/Meet/Teams 等固定几款应用 SDK 的集成工具,而是监听真实对话特有的麦克风+系统音频模式。这意味着 Google Meet、Zoom、Microsoft Teams、Webex、Slack 小组通话、Discord、FaceTime、WhatsApp 通话,甚至通过 Mac 转接的电话,只要是双向音频,都能一样用,不需要针对每个应用单独设置。不用记着按哪个按钮,也不会有"刚才是不是在录音"这种不安时刻。
- **完全在你的 Mac 上转录。** [WhisperKit](https://github.com/argmaxinc/WhisperKit) 运行在 Apple Silicon 的神经网络引擎上——音频绝不会离开你的设备。
- **分得清你说的话和别人说的话。** 麦克风和系统音频分开采集,因此摘要和洞察能准确归属到正确的人。
- **把转录内容变成有用的东西**——标题、要点摘要、行动事项,还可以选择获得一段诚实的反馈,了解你在那次具体对话(无论是一对一、客户电话还是设计评审)中的表现如何。
- **汇总成每日报告**——今天所有会议里发生了什么,你还欠谁什么。

AI 层使用你自己的 [Gemini API 密钥](https://aistudio.google.com/apikey)(免费额度完全够个人使用)——或者干脆不用密钥,在设备上完全本地运行模型。

## 为什么这样设计

- **从设计上就与具体应用无关。** 大多数会议录音工具只能对接几款大厂应用,因为它们要分别集成每家的 SDK。Routine Meeting 则是在系统音频层面采集——只要是在你 Mac 上发声的应用都算数,不管你的团队、客户或家人用的是什么标准。
- **本地优先。** 无论你是否添加 API 密钥,录音和转录都在你的 Mac 上完成。唯一可能离开你设备的东西是文本转录稿,而且只有在你开启云端摘要功能时才会发生。
- **无需账号,无需订阅。** 这是一款原生应用,不是套壳的 SaaS。DMG 是你的,数据也是你的。
- **为真实的会议场景而设计。** 误判(比如音乐声或一段偶然的语音消息)不会变成幽灵录音;通话中麦克风掉线也不会悄悄让你丢失一半的转录内容。

## Routine Meeting 的不同之处

大多数会议助手,不管是用可见的机器人(Fireflies、Otter)还是"无机器人"式采集(Fellow、Fathom),最终还是会把你的录音和转录发送到它们的服务器处理。Routine Meeting 走了另一条路:一切都在你的 Mac 上完成。

- **什么都不会离开你的设备。** 录音和转录完全在设备本地执行。即便和那些标榜"无机器人"的工具相比也是如此,因为"无机器人"只是说没有可见参与者加入通话,并不代表你的数据留在本地。除非你明确开启云端 AI 摘要,否则 Routine Meeting 绝不会上传任何东西。
- **自动适配所有应用。** Routine Meeting 通过监听真实对话特有的麦克风+系统音频模式来识别会议,而不是以参与者身份加入通话,也不依赖某个特定应用的 API。这意味着 Google Meet、Zoom、Teams、Webex、Slack 小组通话、Discord、FaceTime,或是通过 Mac 转接的电话,都能以同样的方式工作,不需要为每个应用单独配置。
- **用自己的密钥,或彻底跳过云端。** AI 摘要可以使用你自己的 Gemini API 密钥(免费额度够个人使用),也可以运行完全本地化的模型,不需要密钥,也不产生任何云端调用。
- **无需账号,无需订阅。** Routine Meeting 完全免费,也不要求你注册任何东西。

### 目前还没有的功能

坦白说:Routine Meeting 是一个人独立开发的 macOS 应用,不是一个有资金支持的平台。Fireflies、Fellow 等类似工具提供、而 Routine Meeting 目前还没有的功能包括:

- 跨会议搜索或长期可检索的知识库(目前仅限于每日汇总)
- 与 CRM、Slack、招聘工具或拨号软件的集成
- 企业合规认证(SOC 2、HIPAA、GDPR)
- Windows 或移动端支持

如果你今天就需要这些功能,Fireflies 或 Fellow 这类平台可能更适合你,尤其是在这些认证很重要的受监管行业。但如果你想要的是那种数据绝不离开 Mac、也不需要机器人(或云端账号)才能运行的工具,Routine Meeting 填补的正是这个空白。

## 安装

1. 从 [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest) 下载最新的 `RoutineMeeting.dmg`。
2. 打开 DMG,把 **Routine Meeting** 拖入**应用程序**文件夹。
3. 启动它。一个简短的设置向导会依次说明每项权限——先解释为什么需要,再弹出系统提示(麦克风、屏幕录制、登录时启动、辅助功能、通知),并让你添加 Gemini 密钥或跳过进入本地模式。屏幕录制这一步用于捕捉其他参与者的音频,并会触发紫色录制指示灯,这是正常且必要的。
4. 你可以随时从菜单栏图标 → **设置向导…** 重新打开这个引导。

超过 7 天且已完成转录的录音会自动删除(转录稿和摘要会永久保留)——可在设置 → 存储空间中调整,也有一个手动的"立即释放空间"按钮。

Routine Meeting 会自动检查更新(通过 [Sparkle](https://sparkle-project.org)),有新版本时会在应用内通知你。

## 隐私

音频和转录内容都保留在你的 Mac 上。除非你开启云端 AI 服务商,否则不会向任何地方发送任何内容——即便开启了,发出去的也只有转录文本,绝不会是原始音频。

这款应用每天还会发送一次匿名 ping(一个不含会议内容、姓名或邮箱的随机 ID),让我能大致了解使用情况。默认开启,你可以随时在设置 → 隐私中关闭,不会影响其他任何功能。

## 反馈 / 问题反馈

在应用内点击菜单栏图标 → **发送反馈…**,或在这里提交一个 [issue](https://github.com/mathguimaraes/routine-meeting/issues)。
