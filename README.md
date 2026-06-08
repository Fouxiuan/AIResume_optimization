# AIResume 项目


基于原项目 AIResume 优化，以下是优化很新增内容。
## 1. AI 接口全面重构 — 从单一厂商到多厂商支持

---
![Pasted image 20260608203333.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608203333.png)
  

## 2. 设置页面完全重写
原版  只有三个输入框，需手动填写所有参数，用户体验较差。
当前版本做了以下改进：
- **厂商预设选择**：提供 6 个 AI 厂商的 Radio 按钮组，一键切换会自动填入对应的 API 地址和推荐模型

- **测试连接按钮**：填写 API Key 后可直接测试连通性

- **厂商文档链接**：每个厂商附带"获取 Key →"和"查看文档"链接

- **数据迁移**：`useSettingsStore` 中新增 `migrateOldData()` 函数，自动将旧版 `aliApiKey`/`aliApiUrl` 迁移为新版通用字段

- **响应式适配**：新增移动端/平板端断点样式
预设厂商配置表：

```

DeepSeek    → https://api.deepseek.com/chat/completions

OpenAI      → https://api.openai.com/v1/chat/completions

阿里云百炼   → https://dashscope.aliyuncs.com/compatible-mode/v1/chat/completions

Moonshot    → https://api.moonshot.cn/v1/chat/completions

智谱 AI     → https://open.bigmodel.cn/api/paas/v4/chat/completions

自定义      → 用户手动填写

```

---

  

## 3. 新增「AI 智能生成简历」页面


用户输入自然语言描述，AI 自动生成一份完整的结构化简历数据：
- 支持流式输出，实时展示生成进度

- 生成结果预览弹窗，确认后可一键应用到简历

- 草稿自动保存到 localStorage，刷新不丢失

- 生成历史记录（最多 20 条），可查看/回填/删除

![Pasted image 20260608203502.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608203502.png)


---

  

## 6. 简历编辑页面的移动端适配

  

- **移动端 Tab 切换**：编辑/预览通过 Tabs 切换，不再并排显示

- **按钮组响应式**：小屏时隐藏按钮文字，仅显示图标

![Pasted image 20260608203536.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608203536.png)
![Pasted image 20260608203548.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608203548.png)
  

---
## 7. AI 深度交流页面优化

- 新增 "AI 帮答"模式

- UI 改进：左侧聊天区和右侧输入区间新增分隔线 (divider)

- 引导步骤描述更新（新增"AI 帮答"选项提及）

- 完整响应式适配（1024px / 768px / 480px 断点）

- 阴影和圆角等视觉细节优化
![Pasted image 20260608203636.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608203636.png)  
![Pasted image 20260608204054.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608204054.png)
![Pasted image 20260608204155.png](https://github.com/Fouxiuan/AIResume_optimization/blob/93d14f5f3b5165114b732831ab3727ba112d1327/public/Pasted%20image%2020260608204155.png)

---

  

## 总结

  

当前项目相比原项目的核心改进方向：

  

1. **AI 生态开放**：从绑定单一厂商（阿里云）变为兼容 6 家主流 AI 厂商，用户可自由选择性价比最高的模型

2. **功能增强**：新增 AI 一键生成简历 + 校园经历模块，覆盖更多使用场景

3. **移动端体验**：从"不支持移动端"变为完整的响应式适配，移除 NarrowScreen 占位，实现真正的移动端可用

4. **用户体验**：设置页面智能化（预设/测试连接）、导航层级优化、数据自动迁移

5. **项目归属**：所有品牌链接和标识更新为新的仓库地址
