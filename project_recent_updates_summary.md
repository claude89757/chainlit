# Chainlit 项目最近更新总结

## 项目概述

**Chainlit** 是一个开源的Python框架，用于快速构建生产级的对话式AI应用程序。该项目目前处于社区维护状态，自2025年5月1日起由社区维护者团队负责维护。

## 最近活动概况

- **最近一个月内提交数量**: 22次提交
- **最新提交**: b8e6f37 - "feat: Reduce LiteralAI dependencies"
- **版本状态**: 当前版本为 2.5.5 (2025-04-14发布)

## 主要近期更新 (基于最新20次提交)

### 🚀 新功能和改进

1. **减少LiteralAI依赖** (#2245)
   - 优化了项目依赖，减少对LiteralAI的依赖

2. **Python 3.13支持** (#2244)
   - 在CI测试矩阵中添加了Python 3.13支持

3. **UI界面优化**
   - 修复了输入框间距问题 (#2246)
   - 为Dialog Portal添加了container属性，支持在Copilot的Shadow DOM中渲染 (#2251)

4. **认证和权限**
   - 为Cognito认证提供者添加了scope环境变量 (#2137)
   - 允许新版本的Starlette框架 (#2238)

5. **存储和持久化**
   - 修复了DynamoDB持久化中float/Decimal转换问题 (#2133)
   - S3 URL不再硬编码，支持localstack S3使用 (#2233)
   - 添加了Google Cloud Storage适配器的ADC支持 (#2212)

### 🔧 技术改进

6. **用户界面增强**
   - 为小屏幕设备折叠命令按钮为图标 (#2168)
   - 修复了聊天设置对话框中取消按钮的问题 (#1897)
   - 添加了警告样式切换器 (#1900)
   - 在元素中包含了mime类型 (#2176)

7. **依赖更新**
   - 升级asyncer到0.0.8版本 (#2214)
   - 解决了Python Logger警告问题 (#2173)

8. **新功能组件**
   - 实现了AskElementMessage - 自定义元素中的时间限制表单 (#2217)
   - 为Select Portal添加了container属性 (#2194)
   - 在启动器中添加了命令功能 (#2149)

## 版本2.5.5的主要特性 (2025-04-14)

### ✨ 新增功能
- 头像现在支持名称中包含`.`字符（会被替换为`_`）
- 为用户会话添加了类型化的会话访问器
- 允许为custom_js或custom_css的标签设置属性
- 在侧边栏悬停过去的聊天时会显示完整标题的工具提示
- 自动设置`X-Chainlit-Session-id`头部以便于WebSocket的粘性会话
- `cl.ErrorMessage`现在有不同的头像
- 复制按钮现在只在运行的最终消息上显示
- CopilotFunction现在可在自定义JS中使用
- 头部链接现在有可选的`display_name`来在图标旁显示文本
- Chainlit加载的默认.env文件现在可通过`CHAINLIT_ENV_FILE`配置

### 🔄 变更
- **[破坏性变更]**: `http_referer`、`http_cookie`和`languages`不再直接在会话对象中可用。现在提供`environ`，包含所有这些以及其他HTTP头部
- 滚动到底部的动画现在是平滑的

## 项目状态

### 维护情况
- 项目现在由社区维护 (@Chainlit/chainlit-maintainers)
- 维护者负责代码审查、发布和安全
- Chainlit SAS不提供未来更新的保证

### 技术栈
- **后端**: Python (>=3.10)
- **前端**: TypeScript/React with Shadcn/Tailwind
- **包管理**: pnpm (工作空间配置)
- **测试**: Cypress
- **代码质量**: ESLint, Prettier, Husky

### 开发工具
- 支持Poetry和pnpm工作空间
- 配置了pre-commit钩子
- 包含完整的CI/CD流程

## 安全更新

项目一直在积极解决安全问题，包括：
- 升级依赖项以解决安全漏洞
- 增强文件相关端点的认证
- 修复路径遍历保护

## 总结

Chainlit项目保持着活跃的开发状态，最近一个月有22次提交，主要集中在：
1. 依赖优化和兼容性改进
2. 用户界面和用户体验优化
3. 安全性和稳定性增强
4. 新功能开发和现有功能完善

项目转为社区维护模式，但依然保持着良好的开发节奏和代码质量标准。