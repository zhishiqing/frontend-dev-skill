---
name: frontend-dev-workflow
description: 前端开发工作流。基于 VoltAgent/awesome-design-md 推荐合适的设计系统，生成项目前端风格指南文档 (FRONTEND_STYLE.md)。触发场景：任何前端组件开发、页面构建、UI 设计和 Web 应用开发任务。
---

# 前端开发工作流

当用户请求进行前端开发时，**必须**遵循此工作流：

## 核心原则

1. **设计系统优先**：优先从 VoltAgent/awesome-design-md 选择成熟设计系统作为模板
2. **用户确认后执行**：设计方案需用户确认后再进行开发
3. **风格文档输出**：每个前端项目必须生成 `FRONTEND_STYLE.md` 风格指南

---

## 必备 Skill 下载与安装

**重要**：在开始前端开发前，必须确保已安装以下两个 Skill。如果用户没有安装，请先指导其下载导入：

### 1. Frontend-design（前端设计 Skill）

- **下载地址**：https://mcpservers.org/claude-skills/anthropic/frontend-design
- **定位**：前端设计专家
- **功能**：接收需求描述，直接输出 HTML+CSS 代码，带响应式布局

### 2. Interaction-design（前端交互设计 Skill）

- **下载地址**：https://github.com/wshobson/agents/tree/main/plugins/ui-design/skills/interaction-design
- **定位**：交互动效专家
- **功能**：微交互、状态反馈、过渡动画

### 安装步骤

1. 访问对应下载地址获取 Skill 文件
2. 将 Skill 文件放置到 应用 的 skills 目录中
3. 重启 应用 使 Skill 生效

---

## 设计系统资源

**参考地址：** https://github.com/VoltAgent/awesome-design-md

VoltAgent/awesome-design-md 包含 73 个从热门网站提取的 DESIGN.md 设计系统文件，涵盖：
- AI & LLM 平台（Claude、Minimax、xAI 等）
- 开发工具（Cursor、Vercel、Expo 等）
- 后端/数据库（Supabase、MongoDB 等）
- 生产力 SaaS（Linear、Notion、Notion 等）
- 金融科技（Stripe、Revolut 等）
- 电商零售（Shopify、Nike、Airbnb 等）
- 汽车品牌（Tesla、BMW 等）

---

## 工作流程

### Step 1: 需求分析与项目类型识别

1. 理解用户的前端需求：
   - 项目类型（AI 平台、开发工具、SaaS、电商等）
   - 目标用户群体
   - 核心功能
   - 品牌调性（专业/活泼/简约/科技感等）

2. 确定项目风格关键词：
   - 深色/浅色主题偏好
   - 简约/丰富密度
   - 现代/经典风格
   - 科技感/亲和力

### Step 2: 推荐设计系统

**必须**从 https://github.com/VoltAgent/awesome-design-md 中根据项目类型筛选 3-5 个合适的设计系统进行推荐。

#### 推荐格式

```
## 设计系统推荐

根据项目类型 **[项目类型]**，推荐以下设计系统供参考：

| # | 设计系统 | 整体风格 | 核心特点 | 适用场景 |
|---|----------|----------|----------|----------|
| 1 | [名称] | [风格描述] | [核心特点] | [适用场景] |
| 2 | [名称] | [风格描述] | [核心特点] | [适用场景] |
| 3 | [名称] | [风格描述] | [核心特点] | [适用场景] |

### 各设计系统对比

#### 1. [设计系统 A]
- **整体风格**：[描述]
- **色彩特点**：[主色调、强调色]
- **字体风格**：[字体选择]
- **组件特点**：[按钮、卡片等风格]
- **适合理由**：[为何适合当前项目]

#### 2. [设计系统 B]
- ...（同上格式）

#### 3. [设计系统 C]
- ...（同上格式）

---

**请选择您偏好的设计系统（输入编号或名称），确认后将以此作为项目整体风格模板。**
```

### Step 3: 获取并应用选定设计

当用户确认设计系统后：

1. **获取 DESIGN.md**
   ```
   访问：https://getdesign.md/[设计系统名称]/design-md
   或访问 GitHub 仓库获取源文件
   ```

2. **提取设计要素**
   从选定的 DESIGN.md 中提取：
   - 颜色系统（主色、辅助色、强调色、背景色）
   - 字体系统（标题字体、正文字体、字号层级）
   - 组件样式（按钮、输入框、卡片、导航等）
   - 间距系统（基础间距单位、常用间距）
   - 阴影与层级
   - 动效风格

3. **调用设计 Skill**
   在前端开发过程中，需要调用这两个 Skill：
   - **frontend-design Skill**：用于生成 HTML+CSS 代码和响应式布局
   - **interaction-design Skill**：用于微交互、状态反馈、过渡动画

### Step 4: 设计执行与开发

基于选定的设计系统进行开发：

1. **frontend-design Skill**：接收需求，输出 HTML+CSS 响应式代码
2. **interaction-design Skill**：实现微交互、状态反馈、过渡动画
3. 保持与设计系统的一致性

### Step 5: 生成风格文档

每个前端项目完成后，**必须**生成 `FRONTEND_STYLE.md` 文档：

```markdown
# [项目名] 前端风格指南

## 设计来源

本项目的设计系统基于 [选定设计系统名称] 设计系统进行定制。

**参考来源：** https://getdesign.md/[设计系统]/design-md

## 设计理念

[描述项目的设计方向和美学追求]

## 视觉规范

### 颜色系统
| 用途 | 色值 | 变量名 | 来源 |
|------|------|--------|------|
| 主色 | #xxx | --color-primary | [设计系统] |
| ... | ... | ... | ... |

### 字体
- 标题字体：[字体名称] - 来源：[设计系统]
- 正文字体：[字体名称] - 来源：[设计系统]

### 间距系统
| 名称 | 值 | 用途 |
|------|-----|------|
| xs | 4px | 紧凑间距 |
| sm | 8px | 小间距 |
| md | 16px | 基础间距 |
| ... | ... | ... |

### 组件样式

#### 按钮
[设计系统定义的按钮样式]

#### 输入框
[设计系统定义的输入框样式]

#### 卡片
[设计系统定义的卡片样式]

## 动效规范

### 时间曲线
[设计系统定义的动画缓动函数]

### 组件动效
| 组件 | 动效类型 | 参数 |
|------|----------|------|
| Button | hover | scale: 1.02, duration: 150ms |
| ... | ... | ... |

## 组件清单

### 基于 [设计系统] 的组件
- [组件名] - 功能描述 - 源码位置

### 自定义组件
- [组件名] - 功能描述 - 源码位置

## 使用示例
[关键组件的使用代码示例]
```

---

## 设计系统选择参考表

| 项目类型 | 推荐设计系统 |
|----------|-------------|
| AI/LLM 平台 | Claude、Cohere、Minimax、xAI、VoltAgent |
| 开发工具/IDE | Cursor、Vercel、Raycast、Expo、Warp |
| 数据库/后端 | Supabase、MongoDB、ClickHouse、PostHog |
| 项目管理 | Linear、Mintlify、Notion |
| 金融/支付 | Stripe、Revolut、Coinbase |
| 电商/零售 | Shopify、Airbnb、Nike |
| 消费电子 | Apple、NVIDIA、Spotify |

---

## 注意事项

1. **设计系统优先**：除非用户明确要求自定义设计，否则优先从设计系统库选择
2. **一致性**：严格按照选定设计系统的规范执行
3. **性能优先**：使用 CSS transform 和 opacity 实现流畅动画
4. **无障碍支持**：始终考虑 prefers-reduced-motion
5. **保持一致性**：项目内的动效风格应保持统一
