# NULL SECTOR // 虚空扇区

> 哨戒协议 NULL-07 已失效。清除全部敌对信号，重建上行链路。

单文件网页第一人称 **波次生存射击游戏**。打开 `index.html` 即玩 —— 无后端、无构建步骤、无需安装，存档保存在浏览器本地。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 快速开始

```bash
git clone https://github.com/zwkwwwwww/null-sector.git
cd null-sector
```

然后用浏览器打开 `index.html` 即可（或起一个本地静态服务器：`python -m http.server 8000`，访问 <http://localhost:8000>）。

首次运行需要联网 —— three.js r128 与后处理着色器从 CDN 拉取；引擎加载完成后即可离线游玩。

> 推荐桌面端 Chrome / Edge（需要鼠标）。手机与平板同样可玩：内建触屏虚拟摇杆与操作按键，支持横竖屏与左手模式。

## 玩法

在 6 张原版战场中抵御一波波敌对信号，击杀得分、拾取补给、拾取武器，撑过全部波次即为肃清成功。

### 武器

| 武器 | 定位 |
| --- | --- |
| VP-7 脉冲手枪 | 无限备弹的制式佩枪，射速快、后坐低 |
| K-9 破障霰弹 | 8 枚弹丸扇形齐发，全武器最强击退 |
| RX-1 轨道步枪 | 超重重弹，弹道几乎无散布，开火伴随 FOV 冲击 |
| HX-4 星爆炮 | 蓄力炮（4 档威力），落点范围爆炸 |
| GAU-2 转管机炮 | 按住预热起转，射速爬升，连续射击积热过热 |
| SW-9 锁定导弹 | 准星压住目标约 0.9 秒完成锁定，制导追踪 |
| PX-9 等离子冲锋枪 | 🔒 隐藏武器 |
| VOID-0 龙息炮 | 🔒 隐藏武器 |

隐藏武器需完成 12 项成就解锁。命中敌人发光核心造成双倍伤害。

### 敌人

哨兵、执行者、狙击者、爆破者、轰炸者 —— 5 种原版敌对单位，行为模式各不相同：预判射击、翻越掩体、超远锁定、自爆冲脸、曲射炮击。爆炸波及敌我双方，可以诱导爆破者在敌群中起爆。

### 难度

| 难度 | 规模 |
| --- | --- |
| 侦察 RECON | 6 波 · 呼吸回血 · 弱敌势 · 无增援 |
| 标准 STANDARD | 9 波 · 呼吸回血 · 波内增援 |
| 肃清 PURGE | 11 波 · 无回血 · 敌潮汹涌 |
| 绝境 ONSLAUGHT | 11 波 · 无回血 · 敌势 ×1.35 · 增援更密 |
| 无尽 ENDLESS | ∞ 波 · 强度随波爬升 · 无胜利 |

### 其它系统

- **随机事件**：每波按概率触发离子风暴、弹药荒、敌群狂化、双倍积分、重力异常、猎杀令
- **增益与连杀**：狂暴 / 时缓 / 无限弹药 / 护盾过载 / 疾行，连杀倍率累积
- **精英单位**：带特殊强化的变体敌人
- **经济改造**：击杀积累信用点，在军械库升级武器伤害
- **成就系统**：15 项作战成就，附进度条与解锁弹窗
- **本地存档**：最高分、生涯统计、设置与 MOD 全部本地存储，支持导出 / 导入备份

## 操作

| 桌面端 | 触屏 |
| --- | --- |
| `WASD` 移动 | 左半屏虚拟摇杆（跟随式） |
| 鼠标瞄准 / 左键射击 | 右半屏滑动转视角 / 开火键（可选自动开火） |
| `R` 装填 | 装填键 |
| `1`–`9` / 滚轮 切枪 | 切枪键 |
| `空格` 跳跃 | 跳跃键 |
| `ESC` 暂停 | 暂停键 |

设置里可调灵敏度、FOV、准星样式（十字 / 点 / T 形 / 圆+点）、屏幕震动、特效与泛光强度，以及自适应画质档位。

## MOD 与创意工坊

游戏内建创意工坊：主菜单 → 创意工坊，可选择示例 MOD 一键安装，或在右侧 JSON 编辑器手写后「保存并启用」。

仓库另附可视化编辑器 `mod-studio.html`，打开即用，用于产出 MOD JSON：

| 页面 | 能力 |
| --- | --- |
| 地图 | 画布摆放货箱 / 掩体 / 高墙，多选拖拽、对齐、等距、矩形与环形阵列、对称放置、整体镜像旋转、撤销重做 |
| 武器 | 完整数值 + 3D 预览（与游戏内视图模型 1:1）+ 试射，支持部件化自定义枪模 |
| 敌人 | 数值、行为模式与外观预览 |
| 波次 | 5 档难度 × 每档 40 波编成 |
| 机制 | 玩法开关与倍率（护盾、重力、雾效、增援……） |
| 导出 | 实时校验 + 生成 JSON，可复制或下载 |

安装流程：Mod Studio 导出 JSON → 游戏主菜单 → 创意工坊 → 粘贴（或导入文件）→ 保存并启用 → 在作战配置中选择 MOD 地图。

MOD 可以只包含任一区块（纯武器 / 纯敌人 / 纯机制 / 纯地图），按列表顺序生效，后装覆盖同名项。

## 目录结构

```
null-sector/
├── index.html          # 游戏本体（单文件）
├── mod-studio.html     # 可视化 MOD 编辑器（单文件）
├── docs/
│   ├── CHANGELOG.md    # v3.1 变更说明
│   └── mobile-controls.md  # 移动端操作对标与优化方案
├── LICENSE
└── README.md
```

## 技术栈

- **three.js r128**（CDN）+ UnrealBloomPass 后处理泛光
- **WebAudio** 程序化合成音效 —— 不含任何音频素材文件
- **localStorage** 存档，支持导出 / 导入
- 纯原生 JavaScript + CSS，**无打包器、无框架、无 npm 依赖**

## 文档

- [v3.1 变更说明](docs/CHANGELOG.md)
- [移动端操作对标与优化方案](docs/mobile-controls.md)

## 授权

[MIT](LICENSE)

---

## English

**NULL SECTOR** is a single-file browser first-person wave-survival shooter. Open `index.html` and play — no backend, no build step, no install. Progress is stored in your browser.

- 6 sector maps, 6 standard weapons + 2 unlockable hidden ones, 5 enemy types, 5 difficulty tiers (including endless), random per-wave events, kill-combo multipliers, buffs, elite units, a credit-based weapon upgrade economy and 15 achievements.
- Bilingual UI (中文 / English), touch controls for mobile with landscape re-layout, and an adaptive quality system.
- A full **mod workshop**: an in-game JSON editor plus the visual `mod-studio.html` editor for maps, weapons, enemies, wave compositions and gameplay mechanics.
- Built with three.js (CDN), WebAudio-synthesised sound and localStorage. No bundler, no framework, no npm dependencies.

Internet is required on first load (the engine is fetched from a CDN); afterwards the game runs offline.

## License

[MIT](LICENSE)
