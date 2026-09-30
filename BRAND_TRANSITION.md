# Nexa doctor 来源与发布边界

日期：2026-09-30。迁移编号：`NX-2026-0001`。

本仓继承 [demisugar-doctor](https://github.com/28257whoami/demisugar-doctor) 的提交
`8962af55d52f03972e500c84de36a8d446a62811`，完整保留历史与许可证。
本地目录已改为 `nexa-doctor`，[Nexa 新仓](https://github.com/28257whoami/nexa-doctor)保持公开。
旧远端已改名为 `upstream`；新的 `origin` 已接到 Nexa 仓，默认推送目标为 origin。
Nexa `main` 已以上述原始提交建立继承基线；本次文档迁移通过 PR 审核，新 Nexa release 尚未发布。

当前只更新文档。Go module 仍为 `github.com/28257whoami/demisugar-doctor`，
工具可执行文件名 `agent-doctor` 是通用工具名，继续保留。
消费方 bootstrap 仍下载 demisugar 的固定 release；完成 Nexa 工具源码与发布迁移后，
再对各消费仓显式升级 release URL、版本及四平台 SHA256，不伪造或沿用新构建的校验和。

本仓保持通用检查职责，不加入产品特有检查、不复制私有产品文档或设计材料。
既有 fixture、历史说明与许可证保留准确语义；新增迁移记录使用 `NX-`，不改写历史来源。
