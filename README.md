# 🎵 Music Genre Finder

> **智能音乐风格查询助手** - 基于 RateYourMusic 的 5947 个音乐风格数据库

[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-5C6BC0)](https://claude.ai/claude-code)
[![Genres](https://img.shields.io/badge/Genres-5947-FF6B6B)](https://rateyourmusic.com/genres/)
[![Categories](https://img.shields.io/badge/Categories-49-4ECDC4)](https://rateyourmusic.com/genres/)

## ✨ 为什么需要这个 Skill？

当你想创作音乐、探索新风格、或者只是想找到"那种感觉"的音乐时，你需要的不是搜索引擎，而是一个懂音乐的助手：

- 🎯 **精确查询** - "查一下 Shoegaze"，立即得到完整信息 + 链接 + 子分类
- 🧠 **智能推荐** - "推荐适合深夜的音乐风格"，根据氛围、场景智能匹配
- 🌳 **层级探索** - "Ambient 下面都有什么"，像树状图一样浏览风格分支
- 🎼 **创作辅助** - 与 Suno 音乐生成集成，为你的音乐选择最合适的风格标签

## 📊 数据规模

这不是一个简单的风格列表，而是一个完整的音乐风格知识库：

```
5947 个音乐风格
├── 49 个主分类 (Rock, Jazz, Electronic, Ambient...)
├── 737 个子分类 (Shoegaze, Lo-fi Hip Hop, Vaporwave...)
└── 5161 个细分风格 (Blackgaze, Hardvapour, Future Funk...)
```

每个风格都包含：
- ✅ 官方英文描述（来自 RateYourMusic）
- ✅ 完整层级关系（主分类 → 子分类 → 孙分类）
- ✅ 直达链接（深入了解历史、代表艺人、专辑推荐）

## 🚀 快速开始

### 安装

1. 下载 `music-genre-finder.skill` 文件
2. 在 Claude Code 中运行：
   ```bash
   claude skills install music-genre-finder.skill
   ```

### 基础用法

#### 1️⃣ 精确查询

只需要问：

```
"查一下 Vaporwave"
"什么是 Shoegaze？"
"Dark Ambient 是什么风格？"
```

**得到完整信息**：

```
🎵 Vaporwave
📝 Nostalgic, surrealist take on elevator music, sampling 1980s-90s
    muzak, smooth jazz, and lounge music, often with a chopped and
    screwed aesthetic.

🔗 https://rateyourmusic.com/genre/vaporwave/

📂 Electronic > Vaporwave

💡 Vaporwave 有 5 个子分类：
  - Hardvapour（更激进的变体）
  - Mallsoft（商场环境音乐）
  - Future Funk（融合 Funk 元素）
  - Eccojams（循环和失真）
  - Signalwave（广播信号美学）
```

#### 2️⃣ 智能推荐

描述你想要的感觉：

```
"推荐一些适合深夜、有点空灵的风格"
"我想要有活力、适合运动的音乐风格"
"推荐一些暗黑、压抑的风格"
"适合写代码时听的音乐风格有哪些？"
```

**基于场景/氛围智能匹配**：

```
🌙 根据"深夜 + 空灵"，为你推荐以下风格：

1. ⭐ Dark Ambient
   "强调阴暗、忧郁和不和谐的氛围"
   🔗 https://rateyourmusic.com/genre/dark-ambient/

2. ⭐ Space Ambient
   "流动而放松的合成器音乐，常围绕外太空意象"
   🔗 https://rateyourmusic.com/genre/space-ambient/

3. ⭐ Drone
   "持续或重复的声音、音符或音簇，强调音色变化"
   🔗 https://rateyourmusic.com/genre/drone/
```

#### 3️⃣ 层级探索

像浏览文件夹一样探索音乐世界：

```
"Ambient 下面都有什么？"
"给我看看 Electronic 的分支"
"Rock 有哪些子分类？"
```

**完整树状结构**：

```
🎵 Ambient 的子分类树：

Ambient （主分类）
├── Ambient Americana
│   └── 使用传统美式乡村乐器，营造田园氛围
├── Dark Ambient ⭐
│   ├── Black Ambient（融合黑金属元素）
│   ├── Ritual Ambient（仪式感、神秘）
│   └── ...
├── Space Ambient
│   └── 太空主题，合成器为主
└── Tribal Ambient
    └── 结合全球传统乐器和氛围
```

## 🎨 使用场景

### 音乐创作

```
你："我想用 Suno 生成一首歌，但不知道用什么风格"
助手："好的！想要什么氛围？我可以帮你推荐：
      1. Synthwave（复古电子，80年代感）
      2. Lo-fi Hip Hop（放松、学习背景音乐）
      3. Shoegaze（空灵、吉他噪音墙）"

你："有活力的"
助手："推荐：Drum and Bass, Hardcore Punk, Electro House"

[自动调用 suno-music-creator，tags 包含选中的风格]
```

### 音乐学习

```
"Shoegaze 和 Dream Pop 有什么区别？"
"Vaporwave 是从什么风格演化来的？"
"给我看看 Jazz 的完整分支树"
```

### 歌单策划

```
"推荐一些适合咖啡店播放的音乐风格"
"我想做一个适合深夜开车的歌单，推荐风格"
"有哪些适合集中注意力工作的音乐风格？"
```

## 🛠️ 技术特性

### 渐进式数据加载

- ✅ **高效** - 不会一次性加载所有 5947 个风格
- ✅ **智能** - 先读 13KB 索引，按需加载具体分类
- ✅ **快速** - 单次查询通常只读取 1-3 个文件（< 30KB）

### 语义匹配引擎

内置关键词映射表，理解你的自然语言描述：

| 你说的 | 系统理解的 | 推荐方向 |
|--------|-----------|---------|
| 深夜、放松、冥想 | ambient, atmospheric, calm | Ambient, Drone, Space Ambient |
| 有活力、激烈 | energetic, fast, aggressive | Punk, Hardcore, Drum and Bass |
| 暗黑、压抑 | dark, gloomy, ominous | Dark Ambient, Black Metal, Industrial |
| 空灵、梦幻 | ethereal, dreamy, reverb | Dream Pop, Shoegaze, Ambient Pop |
| 电子、科技感 | electronic, synthetic, futuristic | Techno, IDM, Ambient Techno |
| 复古、怀旧 | vintage, retro, nostalgic | Synthwave, Vaporwave, Chillwave |

### 与其他 Skills 集成

- 🎼 **suno-music-creator** - 自动为音乐生成选择风格标签
- ✍️ **qiaomu-writer** - 为音乐风格解读文章提供详细信息

## 📁 数据结构

```
skill-source/
└── references/
    ├── _index.json          # 49个主分类索引（13KB）
    ├── _meta.json           # 元数据（399B）
    ├── main/                # 49个主分类文件
    │   ├── ambient.json     # Ambient 及其直接子分类
    │   ├── rock.json        # Rock 及其直接子分类
    │   └── ...
    └── detailed/            # 578个详细分类文件
        ├── dark-ambient.json    # Dark Ambient 的孙分类
        ├── shoegaze.json        # Shoegaze 的孙分类
        └── ...
```

每个风格的数据格式：

```json
{
  "name": "Dark Ambient",
  "url": "https://rateyourmusic.com/genre/dark-ambient/",
  "description": "Emphasizes an ominous, gloomy, and dissonant atmosphere.",
  "level": "sub",        // main, sub, sub-2, sub-3, sub-4
  "parent": "Ambient"    // 父分类名称
}
```

## 🌟 为什么选择 RateYourMusic？

[RateYourMusic](https://rateyourmusic.com/) 是全球最专业的音乐风格分类数据库：

- ✅ **权威** - 由音乐爱好者和专业人士共同维护
- ✅ **全面** - 覆盖从主流到小众的 5947 个风格
- ✅ **准确** - 每个风格都有精确的英文描述和层级关系
- ✅ **活跃** - 持续更新，涵盖新兴音乐风格

## 📝 开发说明

### 数据来源

所有数据抓取自 [RateYourMusic Genres](https://rateyourmusic.com/genres/)（2026-01-31）

### 文件说明

- `music-genre-finder.skill` - 打包好的 Claude Code skill 文件（直接安装即用）
- `skill-source/` - Skill 源代码（包含完整的 references 数据库）

## 📄 许可证

数据来源于 RateYourMusic，仅供个人学习和研究使用。

## 🙋 作者

Created by 乔帮主 with Claude Code

---

<div align="center">

**如果这个 Skill 对你有帮助，请给个 ⭐ Star！**

[安装使用](https://claude.ai/claude-code) · [反馈问题](https://github.com/joeseesun/music-genre-finder/issues) · [RateYourMusic](https://rateyourmusic.com/genres/)

</div>
