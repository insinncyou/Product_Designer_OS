
### 临时上传单个 Prompt 文件

前提是 generate-markdown.md 已经作为情報源 / Project file加入当前 ChatGPT Project。Project 中的参考文件会作为该项目内对话的上下文使用。


第一次直接调用

在该 Project 的对话中输入：

```text
请读取项目情報源中的 generate-markdown.md，
并严格按照该文件的定义执行下面的任务。

任务内容：
整理 Hireroo Design System 的整体文档工作流。

输入信息：
- document_purpose: 说明各设计文档的作用、关系和更新流程
- target_audience: Product Designer、Product Manager、Engineer
- source_content:
  - design-philosophy.md
  - design-principles.md
  - DESIGN_v0.1.md
  - design-decision.md
- language: 日语
- output_filename: design-documentation-workflow.md

最终要求：
- 生成实际可下载的 Markdown 文件
- 不要只在聊天中输出 Markdown 代码块
- 完成后按照 generate-markdown.md 的 Quality checklist 自检
```