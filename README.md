# 微光与暗影

一个纯静态的网页版视觉小说（Galgame）。单文件 HTML 驱动，零依赖、零构建、零后端——双击即玩。

## 玩法

在浏览器中打开 `曙光与暗影.html` 即可开始。通过点击推进剧情，遇到分歧点时选择不同分支，剧情走向随之改变。

- **推进剧情**：点击文本区域继续
- **做出选择**：点击选项按钮进入对应分支
- **返回上一节**：点击左上角返回按钮

## 特性

- **单文件架构**：全部样式与逻辑内联于一个 HTML 文件，便于分发与备份
- **分支剧情**：40+ 剧情节点，包含旁白、对话、选择与结局四种类型
- **多线回退**：基于栈结构的剧情回溯，可逐级回退至上一节点
- **角色立绘**：6 名角色的立绘按剧情动态显示与切换
- **场景氛围**：7 张背景图配合场景切换

## 目录结构

```
.
├── 曙光与暗影.html          # 游戏入口（含全部样式与剧情逻辑）
├── images/                  # 图片素材
│   ├── town_square_dusk.jpg      # 场景背景
│   ├── forest_entrance.jpg
│   ├── dark_forest_path.jpg
│   ├── cave_entrance.jpg
│   ├── old_forest_path.jpg
│   ├── cave_altar.jpg
│   ├── town_celebration.jpg
│   ├── leo.png                   # 角色立绘
│   ├── aira.png
│   ├── morgan.png
│   ├── villagerA.png
│   ├── villageChief.png
│   └── illusionMorgan.png
└── .gitignore
```

## 运行方式

无外部依赖，不需要安装任何东西。

```bash
# 方式一：直接用浏览器打开
start 曙光与暗影.html

# 方式二：本地起一个静态服务器（推荐，避免个别浏览器的本地文件限制）
python -m http.server 8000
# 然后访问 http://localhost:8000
```

## 技术说明

- 纯原生 HTML / CSS / JavaScript，未使用任何框架或第三方库
- 剧情数据集中于 `storyData` 数组，每个节点包含 `type`、`speaker`、`content`、`bgImage`、`showCharacters`、`choices`、`nextIndex` 等字段
- 图片通过相对路径 `images/...` 引用，保持目录结构即可正常加载

## 说明

本仓库为私有仓库，仅用于个人作品存档。
