# 火力不足 / Low Firepower

一个为 **TACZ（Timeless and Classics Zero，枪械 mod）** 设计的 **Curios 战斗饰品扩展**。

- modId：`low_firepower`
- 版本：`1.0.0-r2`
- 环境：**Minecraft 1.20.1 / Forge 47.4+**
- 依赖：[Curios](https://www.curseforge.com/minecraft/mc-mods/curios) `[5.14.1, 6.0)`、[TACZ](https://www.curseforge.com/minecraft/mc-mods/tacz) `[1.0,)`
- 作者署名：AutoMods

> ⚠️ `mods.toml` 中 license 声明为 **All Rights Reserved**。若打算公开分享/允许他人自由使用，请自行决定改为开源协议（如 MIT）。

## 它做什么

新增一个 **Curios 饰品槽「火力不足」（firepower）**，给每个玩家 6 格（`size: 6`，order 500）。玩家把饰品放进去即可获得对应的战斗加成。配套一个按键绑定 **「查看火力不足饰品」**，用于查看当前装备饰品的详情。

## 物品与合成

先做 **火力核心（firepower_core）**：

```
 I G I
 G R G     I=铁锭  G=火药  R=红石
 I G I
```

随后以核心为中心合成 9 种战斗饰品（每种都是 `X C X / C 居中` 形）：

| 饰品 | 配方围绕核心 | 解锁所需材料 |
|------|--------------|--------------|
| 血线 bloodline | 金锭 + 闪烁西瓜片 + 红石 | 金锭 |
| 透视 perspective | 紫水晶 + 玻璃 + 望远镜 | 紫水晶 |
| 旁若无人 indifference | 烈焰粉 + 骷髅头颅 + 箭 | 烈焰粉 |
| 连 chain | 锁链 + 火药 | 锁链 |
| 怒 rage | 烈焰棒 + 火焰弹 | 烈焰棒 |
| 节制 temperance | 青金石 + 皮革 | 青金石 |
| 迅即 swift | 糖 + 兔子脚 + 羽毛 | 糖 |
| 梦 dream | 幻翼膜 + 末影珍珠 | 幻翼膜 |
| 末世 apocalypse | 下界合金碎片 + 凋零骷髅头颅 + 烈焰粉（最高级） | 下界合金碎片 |

> 各饰品的具体战斗数值效果在 `CharmEffects` / 配置类中定义（本仓库未包含编译字节码），进游戏后按「查看火力不足饰品」快捷键查看。

## 目录

```
├── META-INF/mods.toml
├── pack.mcmeta
├── assets/low_firepower/
│   ├── lang/{zh_cn,en_us}.json
│   ├── models/item/*.json        (10 个物品模型)
│   └── textures/**/*.png         (贴图，二进制，未通过本 API 上传)
├── cn/blockforge/generated/lowfirepower/*.class   (编译字节码，二进制，未通过本 API 上传)
└── data/
    ├── curios/tags/items/firepower.json
    └── low_firepower/
        ├── curios/slots|entities/*.json
        ├── recipes/*.json            (10 个合成配方)
        └── advancements/recipes/*.json (10 个配方解锁)
```

## 关于本仓库内容说明

本次通过 GitHub API 提交的是**全部文本资源**（语言文件、物品模型、合成配方、配方解锁、Curios 槽位配置、物品标签、mods.toml）。

以下**二进制文件未包含在本次 API 提交中**（当前上传通道仅支持文本）：

- `cn/blockforge/generated/lowfirepower/*.class` —— 编译后的 Java 字节码（实际逻辑）
- `assets/low_firepower/textures/**/*.png`、`logo.png` —— 贴图

完整可运行的 `low_firepower-1.0.0-r2.jar` 请通过 GitHub 网页「Add file → Upload files」直接拖拽上传，或在 Release 中作为附件发布。
