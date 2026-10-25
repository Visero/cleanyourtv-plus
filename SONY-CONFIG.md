# Sony TV 配置记录（当前生效状态）

记录时间：2026-10-25（从电视端实机读取，非猜测）

## 设备

| 项目 | 值 |
|---|---|
| 型号 | Sony XR-65X90K（BRAVIA VH21，国行） |
| 固件 | STT2.230505.001.S136 |
| 系统 | Android 12 / SDK 31 |
| 局域网 IP | 192.168.31.189 |
| 桌面包 | com.gathin.tvhome（本仓库，versionName 2.5，中文名「极简桌面」） |
| 主页接管 | 已生效（按 Home 直进极简桌面） |

## 当前配置

### 每行应用数量：6

在「简洁桌面设置」中当前选中 **6**（电视端选择，优先级高于编译配置）。

### Dock 程序坞（从左到右，共 6 个）

| 位置 | 应用名 | 包名 | 说明 |
|---|---|---|---|
| 1 | 极空间 | `com.zentraedi.zspace.tv` | NAS 影视 |
| 2 | NewTV极光 | `com.ktcp.tvvideo` | 腾讯视频 TV 版（云视听极光系列） |
| 3 | 云视听小电视 | `com.xiaodianshi.tv.yst` | B 站 TV 版 |
| 4 | 奇异果TV | `com.gitvdemo.video` | 爱奇艺 TV 版 |
| 5 | 酷喵 | `com.cibn.tv` | 优酷 TV 版 |
| 6 | 生活空间装饰 | `com.sony.dtv.livingfit` | 索尼国行预装（Living Decor） |

### 其余设置

| 项 | 值 |
|---|---|
| Rows below dock | 0 |
| 壁纸 | Theme default（如需极光壁纸：`tools/theme.sh themes/aurora`） |
| 动态效果 | 开 |
| 高级动态效果 | 关 |

### 已禁用的系统应用（去广告/遥测，9 个）

```
com.sonyericsson.idd.agent
com.sony.dtv.usercontext
com.qterics.da.product
com.sony.dtv.da.service
com.sony.dtv.braviashow
com.sony.dtv.demosupport
com.sony.dtv.demosystemsupport
com.sony.dtv.multiscreendemo
com.sony.dtv.gestureapp
```

## 本仓库的默认配置（与上表一致）

`launcher/app/src/main/res/values/config.xml`：

- `columns = 6`
- `dock_apps` = 上述 6 个包名，按表格顺序

安装本仓库构建的 APK 后，新装设备默认即为「每行 6 个 + 上述 Dock」。若个别应用未安装，对应槽位会自动被网格应用填充（`fill_dock`），不会留空。
