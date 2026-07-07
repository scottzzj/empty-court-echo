# 空庭回声

《空庭回声》是一款极简风单页 Canvas 肉鸽生存游戏。玩家扮演 Q 版守庭人，在不断扩张的空庭地图中移动、拾取武器、开启宝箱、升级构筑，并连续挑战 10 个关卡 Boss。

在线试玩：

- GitHub Pages：https://scottzzj.github.io/empty-court-echo/
- GitHub 仓库：https://github.com/scottzzj/empty-court-echo

## 游戏特色

- **10 关 Boss 流程**：每关都有独立 Boss，击败第 1-9 关 Boss 后进入下一关，击败第 10 关 Boss 后胜利结算。
- **50 种小兵配置**：小兵按关卡主题和行为模板组织，每关会从敌人池中随机激活 10 种小兵参与刷怪。
- **18 款主武器**：默认武器为 `P-回声手枪`，地图会随机刷新武器，靠近后按 `E` 可以解锁、升级并切换。
- **街机弹幕风格**：包含直线弹、散射弹、激光、扫射激光、旋转弹、追踪弹、分裂弹、地雷、卫星弹等弹型。
- **宝箱与三选一升级**：宝箱开启后消失，只触发一次三选一升级，并会在地图其他位置刷新。
- **完整 HUD**：显示 HP、经验进度、当前关卡、Boss、武器等级和 Overload 状态。
- **本地静态运行**：项目是纯前端静态页面，不依赖构建工具和后端服务。

## 操作方式

| 操作 | 说明 |
|---|---|
| `WASD` / 方向键 | 移动 |
| 鼠标按住 | 优先朝鼠标方向攻击 |
| `E` | 靠近地图武器时升级并切换武器 |
| 靠近宝箱 | 自动开启宝箱并进入三选一升级 |
| `P` | 暂停 / 继续 |
| 页面按钮 | 开始、暂停、重开、音乐开关 |

## 本地运行

推荐使用本地 HTTP 服务打开，避免浏览器对 `file://` 的资源策略差异。

```powershell
cd E:\IdeaWorkSpace
python -m http.server 8765 --bind 127.0.0.1
```

然后访问：

```text
http://127.0.0.1:8765/empty-court-echo/index.html
```

如果只想在项目目录内启动：

```powershell
cd E:\IdeaWorkSpace\empty-court-echo
python -m http.server 8765 --bind 127.0.0.1
```

然后访问：

```text
http://127.0.0.1:8765/index.html
```

## 调试参数

调试参数主要用于验证关卡、武器、敌人和弹幕行为。

| 参数 | 说明 |
|---|---|
| `?debug=1` | 显示对象数量、FPS 和当前状态 |
| `?levelup=1` | 降低首次升级门槛，便于验证三选一 |
| `?stage=1..10` | 从指定关卡开始 |
| `?boss=1..10` | 提前触发指定关卡 Boss |
| `?enemy=enemyId` | 只刷指定小兵，便于验证 50 种小兵配置 |
| `?pattern=laser` | 快速生成指定弹型，可替换为 `straight`、`spread5`、`spiral`、`sweepLaser` 等 |

示例：

```text
http://127.0.0.1:8765/index.html?debug=1&stage=5
```

## 项目结构

```text
empty-court-echo/
├─ index.html          # 游戏主体，包含 Canvas 渲染、输入、战斗和关卡逻辑
├─ PRD.md              # 产品需求文档
├─ README.md           # 中文开源说明
├─ LICENSE             # 项目代码开源许可
├─ LICENSES.md         # 第三方素材许可说明
└─ assets/             # 音频、角色和地图素材
```

## 素材与许可

- 项目代码使用 MIT License 开源，详见 `LICENSE`。
- Kenney 的角色和地牢素材使用 CC0，详见 `LICENSES.md`。
- 背景音乐 `8bit-battle-loop.ogg` 来源于 OpenGameArt，许可为 CC0，详见 `LICENSES.md`。

## 当前版本

当前发布版本：`v1.0.0`

这是一个可试玩的 MVP 版本，重点验证 10 关流程、18 款武器、50 种小兵配置、宝箱刷新、经验升级、Boss 推进和 GitHub Pages 静态发布。
