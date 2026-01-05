# Curator-App 产品功能全景书 (Master Feature List) 

项目核心: 结合 AIGC (生成式 AI) 与 Affiliate (社交分销) 的高端家居生活方式平台。
核心价值: Design (创作) + Curate (选品) + Earn (赚钱)。
设计语言: "Editorial/Old Money"（杂志风）。关键词：沉浸式、暖石色背景、衬线体 (Serif)、无框化 (Borderless)。

## 1. 启动与权限体系 (Onboarding & Auth)

策略核心: “软墙 (Soft Wall)” —— 先体验后注册，极大化漏斗转化。

1.1 启动体验 (Splash & Launch):

Splash Screen: 极简 Logo 呼吸动效，暖石色背景。

过渡逻辑: Splash 消失后，直接展示首页骨架屏 (Skeleton)，而非白屏，等待数据加载。

1.2 沉浸式引导 (Onboarding):

全屏杂志封面风（3页轮播），强调“AI 魔法”、“场景预览”、“佣金收益”。

1.3 登录与软墙 (Auth & Soft Wall):

方式: 仅支持 Apple, Google, Facebook。无邮箱密码注册。

游客权限: 允许浏览 Shop、试玩 Create (限3次/设备)、查看佣金。

拦截点: 点击 Share/Save/Wallet 时触发。

数据继承: 登录后自动恢复游客操作状态（选品/生成图），无缝衔接。

1.4 邮箱订阅 (Growth):

Inner Circle: 登录后弹窗邀请订阅 Newsletter（以趋势报告为诱饵）。

Settings: 提供邮箱修改入口（针对 Apple Hide Email 用户）。

## 2. 核心功能模块 (Core Modules)

🛍️ 模块 A: CURATE (选品中心/首页)

2.1 布局与视觉:

Hero Section: 顶部全宽大图（视觉缓冲）。

Masonry Feed: 双列瀑布流，全出血无框设计。

Earn Badge: 图片左上角悬浮 "✨ Earn $XX" 玻璃质感标签。

2.2 加载体验 (Loading State):

骨架屏: 数据未至时，显示灰色脉冲方块。

图片懒加载:

先显示 “骨架 + 品牌 Logo 水印”。

图片下载完成后 淡入 (Fade-in) 覆盖水印。

2.3 全屏详情页:

主图: 锁定 4:5 竖向比例，默认展示 Living Room 场景。

场景滤镜: 底部悬浮圆圈 (Living/Bed/Dining)，一键切换 (Pre-rendered)。

动态计算器: 选择尺寸 (5x7, 8x10) 时，零售价与佣金实时联动更新。

2.4 核心动作: 底部吸底大按钮 "Share & Earn"（点击即复制链接 + 自动保存）。

🎨 模块 B: CREATE (AI 工作室)

3.1 输入端: 去框化“灵感画布”设计。视觉化风格选项 (Visual Thumbnails)。

3.2 生成体验 (The Wait - 45s):

动画: 全屏 “纹理背景 + CSS 扫描光效” (无 GIF)。

文案: 7条循环播放的 Fact-Based 文案（强调雪尼尔/机洗/美国制造/高转化，而非指导用户）。

进度: 真实感进度条 (先快后慢)。

3.3 结果展示:

默认: 场景图 (In-Room)。

切换: 右下角 "View Texture" 查看白底细节。

数量: 一次生成 2 张高质量变体。

3.4 操作:

魔法滤镜: [More Like This] / [Surprise Me]。

防误触: "Start Over" 放顶部，底部只放 "Save & Share"。

📂 模块 C: PORTFOLIO (资产库)

4.1 列表管理:

筛选: 统一为 All | Active (已赚) | Ready (未发)。

状态: 未激活显示 "Potential $XX" (灰)，已出单显示 "Earned $XX" (绿)。

4.2 高级交互:

长按下载 (Long Press): 长按图片 -> 唤起 Asset Carousel 弹窗 -> 滑动选择下载场景图或白底图。

批量管理: 多选删除功能。

💳 模块 D: REWARDS (钱包)

5.1 视觉: 黑金/磨砂质感卡片。

5.2 全站推广: 顶部展示 "Ambassador Link" (首页链接，30天 Cookie)。

5.3 资金看板: 拆分 Available / Pending / Lifetime。

5.4 提现 (Redeem):

门槛: <$50 显示进度条，>=$50 按钮点亮。

流程: 点击 Redeem -> 弹出 Gift Card Store (Amazon/Starbucks 黑金卡) -> 选择 -> Email 发送。

反馈: APP 内仅提示“发送成功”，不显示 Code。

⚙️ 模块 E: SETTINGS (设置)

6.1 核心板块:

Identity Card: 头像/昵称/登录方式(Badge)。

Mission Card (增长): "Verify Email -> Get 10 Credits" 任务卡片。

Preferences: 邮箱管理、通知开关。

Support: 法律条款 (WebView)、客服。

6.2 合规: 底部包含 "Log Out", "Delete Account" 和 "App Version"。

## 3. 体验与性能细节 (UX & Performance Details)

3.1 弱网与错误处理:

骨架屏 (Skeleton): 所有列表页必须有 Logo 水印骨架。

错误页 (Error State): 网络失败时展示 "Connection Lost" 插画 + 重试按钮。

3.2 交互反馈:

按钮防抖: API 请求期间按钮变 Spinner + Disabled。

3.3 iOS 兼容性:

下载功能强制使用 navigator.share() 调用原生菜单。

## 4. 法律与合规 (Legal & Compliance)

- 文件载体: H5 页面 (index.html)。
- 关键条款:
  - FTC Disclosure: 强制要求用户披露利益关系。
  - AI Disclaimer: 生成内容免责。
  - Independent Contractor: 明确非雇佣关系。
  - Locking Period: 佣金锁定期（默认35天）。
 
