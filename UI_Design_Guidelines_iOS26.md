# UI Design Guidelines (Including iOS 26)

- Project: Universal Product UI Design System
- Version: v1.0
- Language: Chinese
- Last Updated: 2026-03-19
- Scope: iOS / iPadOS primary, Web and Android as extension

## 1. 文档目标

本规范用于统一产品视觉与交互体验，确保设计与开发在以下方面一致：

1. 可识别：统一品牌表达与组件风格
2. 可扩展：支持多端和多业务线快速复用
3. 可访问：满足无障碍与国际化要求
4. 可交付：设计稿、代码与测试标准可直接衔接

## 2. 设计原则

1. 清晰优先：信息层级必须一眼可读
2. 内容优先：装饰不干扰关键任务
3. 渐进披露：复杂流程按步骤展开
4. 及时反馈：所有操作有状态反馈
5. 默认无障碍：在组件层就满足可访问性

## 3. 平台与版本策略

### 3.1 平台分层

- L1（核心）：iOS（含 iPhone、iPad）
- L2（扩展）：Android
- L3（补充）：Web 管理端

### 3.2 iOS 26 适配说明

截至 **2026-03-19**，本章节采用“前瞻兼容策略”：

- 基线规范：Apple Human Interface Guidelines（当前稳定原则）
- 适配目标：为 iOS 26 可能出现的视觉层次、上下文交互和系统智能能力预留接口
- 执行方式：通过 Design Token 与语义化组件隔离系统变更风险

## 4. Design Tokens（设计令牌）

### 4.1 颜色系统

#### 4.1.1 品牌色

- `brand/primary`: `#00BD8D`
- `brand/secondary`: `#30D158`
- `brand/warning`: `#FF9F0A`
- `brand/danger`: `#FF453A`

#### 4.1.2 语义色（Light）

- `bg/base`: `#FFFFFF`
- `bg/elevated`: `#F7F8FB`
- `text/primary`: `#111A34`
- `text/secondary`: `#41485D`
- `border/default`: `#EBEEF2`

#### 4.1.3 语义色（Dark）

- `bg/base`: `#0B0C0F`
- `bg/elevated`: `#13161B`
- `text/primary`: `#F9FAFB`
- `text/secondary`: `#9CA3AF`
- `border/default`: `#2A2F37`

#### 4.1.4 对比度标准

- 普通文本对比度 >= 4.5:1
- 大号文本（>= 18pt Regular 或 >= 14pt Bold）>= 3:1
- 状态色不能仅靠颜色区分，必须配合图标/文案

### 4.2 字体系统（iOS 优先）

- 字体族：`SF Pro`（系统字体）
- 数字：`SF Pro Rounded` 或 `Monospaced Digit`（金额/计时场景）
- 最小字号：`11pt`（仅辅助信息）

#### 4.2.1 字阶

- `Display`: 34/41, Semibold
- `Title1`: 28/34, Semibold
- `Title2`: 22/28, Semibold
- `Headline`: 17/22, Semibold
- `Body`: 17/24, Regular
- `Subhead`: 15/20, Regular
- `Footnote`: 13/18, Regular
- `Caption`: 12/16, Regular

### 4.3 间距与栅格

#### 4.3.1 间距刻度

- `space-2`: 2
- `space-4`: 4
- `space-8`: 8
- `space-12`: 12
- `space-16`: 16
- `space-20`: 20
- `space-24`: 24
- `space-32`: 32

#### 4.3.2 布局规则

- 页面左右安全边距：16
- 卡片内边距：16 或 20
- 组件垂直最小间隔：8
- 8pt 网格对齐，必要时允许 4pt 微调

### 4.4 圆角、描边、阴影

- `radius/sm`: 8
- `radius/md`: 12
- `radius/lg`: 16
- `radius/xl`: 24
- 细描边：1px（低对比背景下可用 0.5px）
- 阴影分 3 层：`shadow-1`（悬浮）、`shadow-2`（弹层）、`shadow-3`（模态）

## 5. 组件规范

### 5.1 Button

#### 5.1.1 类型

- Primary
- Secondary
- Tertiary（文本按钮）
- Destructive

#### 5.1.2 尺寸

- `L`: 高 52，左右内边距 20
- `M`: 高 44，左右内边距 16
- `S`: 高 36，左右内边距 12

#### 5.1.3 状态

- `default` / `pressed` / `disabled` / `loading`
- `disabled`：透明度建议 40%，同时降低边界对比

### 5.2 Input

- 默认高度：44
- 标签与输入框间距：6
- 错误态同时展示：红色边框 + 错误文案 + 图标
- 支持 clear、密码显隐、格式化（手机号/银行卡）

### 5.3 Card

- 默认圆角：16
- 默认内边距：16
- 卡片之间垂直间距：12
- 卡片内层级：标题 > 主内容 > 辅助信息 > 操作

### 5.4 Navigation

- 顶部导航高度遵循系统安全区
- 返回行为统一：左上角返回 + 右滑返回手势
- Tab Bar 图标支持填充/线框两态
- 当前激活态必须同时有颜色和形状变化

### 5.5 Modal / Sheet

- 首选 Bottom Sheet 承载中断性较低任务
- 全屏 Modal 仅用于高专注流程（支付、授权、编辑）
- 关闭路径必须明确：关闭按钮 + 手势下拉（可选）

### 5.6 List

- 行高：最小 52
- 滑动操作：最多 2 个次要动作 + 1 个危险动作
- 列表空态必须包含：说明 + 行动按钮

## 6. 交互与动效

### 6.1 时长与曲线

- 微交互：120ms - 180ms
- 页面切换：220ms - 320ms
- 强调反馈：不超过 400ms
- 缓动：优先 ease-out，避免弹跳过度

### 6.2 反馈规范

- 点击后 100ms 内提供视觉反馈
- 提交后给出 3 态：进行中 / 成功 / 失败
- 对不可逆操作提供二次确认

### 6.3 手势优先级

- 系统手势 > 导航手势 > 业务手势
- 避免边缘冲突（尤其是横向滑动容器）

## 7. iOS 26 前瞻设计要求

> 说明：以下为兼容未来系统演进的“约束式规则”，用于降低升级成本。

### 7.1 语义化层级

- 所有颜色、字号、圆角必须走 Token，不允许写死
- 组件暴露语义属性：`surface-level`, `emphasis`, `intent`
- 禁止在业务页面直接覆盖系统动态字体行为

### 7.2 上下文感知 UI（Context-Aware）

- 支持根据场景切换信息密度（驾驶、办公、夜间）
- 支持关键动作的“预测位”占位（例如智能推荐入口）
- 推荐操作与主任务分离，防止注意力劫持

### 7.3 深度与材质

- 提供 0-3 级表面深度 Token：`surface-0` 至 `surface-3`
- 模糊材质仅用于导航层与临时面板
- 前景文本必须先验证对比度再叠加材质

### 7.4 智能功能接入边界

- AI 生成结果必须标记来源与时间
- 高风险操作（发送、支付、发布）禁止默认自动执行
- 提供“撤销”或“回退”能力，窗口至少 5 秒

## 8. 无障碍与国际化

### 8.1 无障碍

- 点击热区最小 44x44
- VoiceOver 可读名称与 Hint 必填
- 动效可减弱：遵循 `Reduce Motion`
- 色盲友好：关键信息不只靠颜色传达

### 8.2 国际化

- 文案长度预留：中文基线 1x，英文 1.3x，德语 1.5x
- 日期与数字格式遵循系统 Locale
- 支持 RTL（阿拉伯语等）镜像布局

## 9. 设计到开发交付规范

### 9.1 文件结构建议

- `foundations/`：颜色、字体、间距、圆角
- `components/`：组件变体与状态
- `patterns/`：页面模式（列表页、表单页、详情页）
- `prototypes/`：关键流程动效演示

### 9.2 命名规范

- 组件：`Component/Variant/State/Size`
- Token：`category/type/item/state`
- 图层：语义命名，禁止 `Rectangle 123`

### 9.3 开发对齐

- iOS：SwiftUI 优先，UIKit 为兼容层
- 令牌下发：JSON 或 Style Dictionary
- PR 必须包含：视觉截图（Light/Dark）+ 可访问性检查结果

## 10. 质量门禁（Definition of Done）

1. 视觉：与规范偏差 <= 2px（特殊动画除外）
2. 交互：关键链路无阻塞，无死路
3. 无障碍：VoiceOver 可完整操作核心流程
4. 性能：首屏可交互时间达标（按项目 SLA）
5. 兼容：iOS 当前稳定版 + 前一大版本通过回归

## 11. 附录：Token 示例（JSON）

```json
{
  "color": {
    "brand": {
      "primary": "#0A84FF",
      "danger": "#FF453A"
    },
    "text": {
      "primary": {
        "light": "#111827",
        "dark": "#F9FAFB"
      }
    }
  },
  "radius": {
    "sm": 8,
    "md": 12,
    "lg": 16
  },
  "space": {
    "4": 4,
    "8": 8,
    "16": 16,
    "24": 24
  },
  "typography": {
    "body": {
      "size": 17,
      "lineHeight": 24,
      "weight": 400
    }
  }
}
```

---

如需扩展为企业级版本，建议继续补充：

- 设计系统治理流程（评审、发布、废弃）
- 组件可用性测试模板
- 埋点命名和体验指标（任务完成率、误触率、回退率）
