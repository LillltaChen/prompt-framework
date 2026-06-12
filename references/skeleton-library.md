# 骨架库

预设骨架模板。每个骨架定义插槽结构，变量决定最终输出。

## 骨架 1：视觉画面生成（通用）

适用于：AI 绘画 / 海报 / 封面 / 插画 / 摄影合成

```
# 角色
你是一位「{STYLE_NAME}」风格的视觉执行专家，专精{CATEGORY}类画面生成。

# 任务
创作一张 {ASPECT_RATIO} 比例的{CATEGORY}画面，采用「{STYLE_NAME}」视觉系统。

# 风格保真锁定
{STYLE_FIDELITY_ANCHORS}

# 画面内容
主体：{SUBJECT}
动作/状态：{SUBJECT_ACTION}
道具/产品：{PROP}
场景：{LOCATION}
背景：{BACKGROUND}
主文案：{PRIMARY_TEXT}
副文案：{SECONDARY_TEXT}
点缀/氛围：{ACCENT}

# 必须包含
{MUST_INCLUDE}

# 严格避免
{MUST_AVOID}

# 特殊约束
{SPECIAL_CONSTRAINTS}
```

---

## 骨架 2：电商 / 产品封面（骨架 1 的业务定制版）

适用于：种草封面 / 带货主图 / 产品宣传图

```
# 角色
你是一位「{STYLE_NAME}」的锁定执行专家，专精{PLATFORM}电商{CONTENT_TYPE}封面生成。

# 任务
创作一张 {ASPECT_RATIO} 比例的{PLATFORM}{CONTENT_TYPE}种草封面，采用「{STYLE_NAME}」视觉系统。

# 风格保真锁定
{STYLE_FIDELITY_ANCHORS}

# 画面内容
主体：{SUBJECT}
动作：{SUBJECT_ACTION}
产品：{PRODUCT_OR_PROP}
场景：{LOCATION}
背景：{BACKGROUND_ELEMENTS}
主文案：{MAIN_TEXT}
副文案：{SECONDARY_TEXT}
点缀：{ACCENT_ELEMENTS}

# 必须保留
{MUST_RETAIN}

# 严格避免
{SOURCE_CONTENT_TO_AVOID}

# 合规声明
{COMPLIANCE_STATEMENT}
```

**与骨架 1 的区别：** 增加了 `PLATFORM`（发布平台）和 `COMPLIANCE_STATEMENT`（合规声明）两个电商特有变量。其余结构完全一致。

---

## 骨架 3：长文写作

适用于：公众号文章 / 博客 / 教程 / 深度分析

```
# 角色
你是一位「{WRITING_STYLE}」风格的内容创作者，专精{TOPIC_DOMAIN}领域写作。

# 任务
撰写一篇关于 {TOPIC} 的{TEXT_TYPE}，目标读者是 {TARGET_AUDIENCE}，字数 {WORD_COUNT}。

# 风格锁定
语调：{TONE}
句式：{SENTENCE_STYLE}
用词：{WORD_CHOICE}
节奏：{PACING}

# 内容结构
开头钩子：{HOOK}
核心观点：{CORE_ARGUMENT}
支撑素材：{SUPPORTING_MATERIAL}
行动收尾：{CALL_TO_ACTION}

# 必须包含
{TEXT_MUST_INCLUDE}

# 严格避免
{TEXT_MUST_AVOID}
```

---

## 骨架 4：视频脚本

适用于：短视频 / 口播 / 教程视频 / 产品演示

```
# 角色
你是一位「{VIDEO_STYLE}」风格的视频脚本撰写专家。

# 任务
撰写一支 {DURATION} 的{PLATFORM}视频脚本，主题为 {TOPIC}，目标受众为 {TARGET_AUDIENCE}。

# 风格锁定
节奏：{PACING}
人称：{NARRATION_PERSON}
开场方式：{OPENING_STYLE}
结尾方式：{CLOSING_STYLE}

# 脚本内容
[0:00-0:05] 视觉：{VISUAL_OPENING} | 口播/字幕：{HOOK_LINE}
[0:05-0:20] 视觉：{VISUAL_SECTION_1} | 口播/字幕：{CONTENT_1}
[0:20-0:35] 视觉：{VISUAL_SECTION_2} | 口播/字幕：{CONTENT_2}
[0:35-0:45] 视觉：{VISUAL_SECTION_3} | 口播/字幕：{CONTENT_3}
[0:45-0:50] 视觉：{VISUAL_CLOSING} | 口播/字幕：{CTA_LINE}

# 必须出现
{VIDEO_MUST_INCLUDE}

# 严禁出现
{VIDEO_MUST_AVOID}
```

---

## 如何添加新骨架

1. 确定这个任务需要的**层次**（角色任务层 / 风格约束层 / 内容细节层）
2. 每个层列出 **3-8 个插槽**（用 `{VARIABLE_NAME}` 标记）
3. 给每个插槽写一个**占位描述**，描述越具体，AI 填充时越准确
4. 放入本文件，命名为「骨架 N」

新骨架提交后，在 SKILL.md 的阶段 0 的模式 A 中即可引用。
