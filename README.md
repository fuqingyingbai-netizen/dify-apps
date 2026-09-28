# Dify 应用集合

这里收录我在 [Dify](https://dify.ai) 平台上搭建的 AI 应用，全部以 **DSL 文件**（`.yml`）的形式开源，可以直接导入到自己的 Dify 工作区使用或二次修改。

## 应用一览

| 应用 | 类型 | 用途 | 依赖插件 | 目录 |
| --- | --- | --- | --- | --- |
| 出题组卷 | 工作流 | 传入教学文档，自动生成试卷（选择题 / 填空题 / 简答题）并写入飞书文档 | DeepSeek、飞书文档 | [apps/exam-paper-generator](apps/exam-paper-generator) |
| 智能客服 | 高级对话 | 问题分类 + 知识库检索 + 大模型回答的客服机器人 | DeepSeek、ranKGpt | [apps/smart-customer-service](apps/smart-customer-service) |
| 竞品情报自动分析助手 | Agent 对话 | 以 Agent 模式收集与整理竞品情报 | 无（使用 gpt-4o-mini） | [apps/competitive-intel-agent](apps/competitive-intel-agent) |

## 导入到 Dify 的方法

1. 打开 Dify 工作区，进入 **工作室（Studio）**
2. 点击 **创建应用 → 导入 DSL 文件**
3. 选择应用目录下的 `app.yml`
4. 导入完成后，按各应用目录里的 `README.md` 配置插件、模型密钥与知识库

## 重要说明

- **DSL 文件不包含任何密钥**：模型 API Key、飞书应用凭证等都保存在个人工作区设置中，导入后需要自己配置。
- **知识库内容不会随 DSL 导出**：如果应用引用了知识库，导入后需要重新绑定自己的知识库。
- **插件依赖**：部分应用依赖 Dify 市场插件，导入前请先在工作区安装对应插件，否则相关节点无法运行。
- **模型依赖**：工作流里的 LLM 节点需要对应模型供应商的可用额度，例如 DeepSeek 需要在工作区配置 API Key。

## 目录结构

```text
dify-apps/
├── README.md
└── apps/
    ├── exam-paper-generator/      # 出题组卷（工作流）
    │   ├── app.yml
    │   └── README.md
    ├── smart-customer-service/    # 智能客服（高级对话）
    │   ├── app.yml
    │   └── README.md
    └── competitive-intel-agent/   # 竞品情报自动分析助手（Agent 对话）
        ├── app.yml
        └── README.md
```

## 后续计划

- 补充每个应用的截图与演示说明
- 继续把工作区里的其他应用（电商运营分析工作流、电商智能客服助手）整理进来
