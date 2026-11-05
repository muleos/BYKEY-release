# BydNearKey

比亚迪手表蓝牙数字钥匙 · 靠近解锁（HarmonyOS 手机端）。

**本仓库只分发安装包，不含源码。** 下载与历史版本见 [Releases](../../releases)。

有问题、要当天激活口令，或想反馈建议，请加 **QQ 群 974801085**（[一键加群](https://qun.qq.com/universal-share/share?ac=1&authKey=APxySIvcWIfPQjOaM43RswoPZwNSInZZIz04QWGwxaRoYgLJeJpV%2BCMOZfnymooh&busi_data=eyJncm91cENvZGUiOiI5NzQ4MDEwODUiLCJ0b2tlbiI6IlpYQjJGdVRNZmM1MXpPREdOam5Ka3JUUCt5SzFtNUtRZkVkRkFkQ3ltOFY4WU05dG4ra1g4akZEVzVLcytCelciLCJ1aW4iOiIxMTg3NjA3MDcxIn0%3D&data=WPfffiXVTy_2zxiB8dkp2Ylc6HA6GL73eHLnDZwt4CUmnX9xvJfKgll6L30eWgJhvnKCuwdjNnbpkrzaQDd1FA&svctype=4&tempid=h5_group_info)；链接失效用群号搜索）。

| | |
|---|---|
| 包名 | `com.hmos.BydNearkey` |
| 当前版本 | v1.4.66（versionCode 1000228） |
| 最低系统 | HarmonyOS 6.0.0 (API 20) |

## 主要功能

1. **熄屏靠近解锁、远离上锁** —— 走近自动解锁，走远自动落锁，优先蓝牙直连，连不上自动回落云端兜底。
2. **老车主也能蓝牙直连** —— 部分早年车型不走常规随机数握手，程序自动识别后改用它们认的明文帧，手机号取登录账号；走新协议的车不受这条路影响，无需手动选协议族。
3. **锁了就是真锁了** —— 落锁后按 1.5 / 4 / 12 / 30 秒复核车况，只认车端采样晚于下发的新鲜帧，确认没锁就补发一次；四档都过完仍明确未锁，「最近动作」里留一条「锁车失败」。
4. **阈值与灵敏度可调** —— 距离阈值手调；解锁灵敏度 2/4/6 帧，落锁延迟 2.5/4/6 秒。
5. **云端控车** —— 解锁、锁止、开后备箱、闪灯鸣笛、开/关空调；长按温度卡片可预约 20 分钟后开空调。
6. **车况查看** —— 整车状态、门窗、胎压、温度、空调、里程能耗、健康自检，按本车实际支持项显示。
7. **后台不出"某天突然不解锁"** —— 扫描看门狗、解冻检测、建链退避与远场待机，加会话保鲜；后台自检改成判死才提醒，回前台自动复活。
8. **判不清就告诉你卡在哪** —— 「后台检测」页把靠近解锁与远离上锁分成两张诊断卡，各自只显示本方向的关卡。
9. **桌面小组件** —— 1×2 / 2×2 / 2×4 三种尺寸，每张卡片每格都能自选内容（解锁、上锁、上电、熄火、空调、后备箱、应用图标…），可无限添加；
   可选「点卡片直接控车」，在桌面一步下发指令，首次开启需手动输入确认文本以免误触。
10. **锁后提醒** —— 锁车后若车辆未熄火、车窗/天窗没关或后备箱还开着，会推一条通知，并在「最近动作」留一条黄色提醒；同时存在的多项合并成一条。
11. **控车通知** —— 解锁 / 上锁 / 熄火等动作通过系统通知栏即时提醒，可自定义铃声与震动。
12. **不与官方 App 顶登录** —— 以「手表端」身份独立授权，会话独立，可同时登录。

## 下载

| 文件 | 说明 |
|---|---|
| `BydNearKey-vX.Y.Z-unsigned.zip` | App Pack 压缩包，解压得 `.app`；未签名 |
| `BydNearKey-vX.Y.Z-unsigned.hap` | 单 HAP，不用解压；未签名 |

一般直接用最新的 [v1.4.66](../../releases/latest)。GitHub 不接受 `.app` 后缀，故 App Pack 以 `.zip` 提供。

## 安装

```bash
unzip BydNearKey-v1.4.66-unsigned.zip
hdc list targets
hdc install -r BydNear-v1.4.66-unsigned.app    # 未签名包，需先自行签名
hdc install -r BydNearKey-v1.4.66-unsigned.hap # 或直接装单 HAP
```

> 未签名包装到真机需设备已开启开发者模式；长期使用请用自己的证书重新签名。
> versionCode `1000228` 可直接覆盖 v0.9.88 及之后的所有版本，无需先卸载。

## 首次使用

1. 首次打开需输入 6 位激活口令（每天 0 点更新，群里取当天口令）
2. 用手机上的**比亚迪 App** 扫表盘二维码 → 手机点确认
3. 之后靠近车辆自动解锁、离开自动上锁（设置里可关）

## 声明

个人开发者制作的**非官方**工具，与比亚迪（BYD）官方无关，仅供个人学习与自用。
使用本工具产生的任何后果由使用者自行承担，请勿用于商业用途或二次分发。
