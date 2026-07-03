# NoteAI

NoteAI 是一款集成了 AI 能力的现代化 Android 笔记管理应用。它支持 Markdown 渲染、智能标签管理、云端同步以及完善的回收站机制，旨在为用户提供流畅且智能的笔记记录体验。

---

## 🚀 核心功能

### 1. 智能 AI 助手 (Powered by DeepSeek)
*   **AI 摘要**：一键为长篇笔记生成精简摘要，支持插入正文开头。
*   **AI 标签生成**：根据笔记内容智能推荐并生成主题标签，提高组织效率。

### 2. Markdown 深度支持
*   支持 Markdown 语法预览（标题、列表、代码块等）。
*   **富文本渲染**：提供实时预览模式，采用块解析器实现高效渲染。
*   **图片集成**：支持从相机或相册插入图片，自动生成 Markdown 语法。

### 3. 云端账户与同步 (Firebase)
*   **身份验证**：支持邮箱/密码注册与登录，保护用户私密数据。
*   **实时同步**：笔记自动同步至 Google Firebase Cloud Firestore，支持多设备数据同步。
*   **本地优先**：采用本地 Room 数据库缓存，支持离线查看与编辑，联网后自动同步。

### 4. 完善的笔记管理
*   **标签系统**：支持为笔记添加多色标签。主页顶部设有标签过滤栏，支持点击过滤和长按删除。
*   **回收站 (Trash)**：笔记删除后进入垃圾箱，支持一键恢复或彻底删除，防止误删。
*   **批量操作**：支持主页长按进入多选模式，进行批量删除同步。
*   **侧边栏 (Sidebar)**：快速切换笔记列表、查看垃圾箱、管理个人账户及同步状态。
*   **拖拽删除**：在侧边栏支持将笔记直接拖拽至垃圾箱图标进行快速软删除。

---

## 🛠️ 技术栈与配置

### 开发环境
*   **语言**：Kotlin
*   **Target SDK**：35 (Android 15)
*   **数据库**：Room Database (本地) + Firebase Firestore (云端)
*   **身份验证**：Firebase Auth
*   **网络**：OkHttp 4.12.0
*   **UI 组件**：Material Design 3, SwipeRefreshLayout, Flexbox (ChipGroup)

### 环境配置
1.  **Firebase 配置**：
    *   在根目录 `app/` 下放置 `google-services.json` 文件。
    *   在 Firebase 控制台启用 `Email/Password` 登录方式。
    *   设置 Firestore 规则以允许已验证用户读写。
2.  **AI API 配置**：
    *   在 `local.properties` 文件中添加：
        ```properties
        OPENAI_API_KEY=您的_DEEPSEEK_API_KEY
        ```
    *   当前配置使用 DeepSeek 官方接口：`https://api.deepseek.com/chat/completions`

---

## 📸 界面预览
*   **主页面**：网格布局展示，顶部标签过滤，支持多选。
*   **详情页**：沉浸式编辑体验，AI 功能集成，Markdown 实时预览。
*   **侧边栏**：用户信息展示，快捷功能入口。

---

## 📅 下一阶段计划
*   增加本地笔记导出为 PDF/Markdown 文件功能。
*   集成更多 AI 能力（如：智能纠错、内容续写）。
*   优化多图混排的排版性能。
