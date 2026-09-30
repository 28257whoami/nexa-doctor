# nexa-doctor

Nexa 独立维护的通用仓库一致性检查器，继承 `demisugar-doctor`，保留原 Git 历史。
工具命令继续叫 `agent-doctor`；它检查文档链接、规则适配器、生成索引和显式能力声明，
不承载私有产品资料，也不替业务仓执行构建或测试。

来源和迁移状态见 [BRAND_TRANSITION.md](BRAND_TRANSITION.md)，工程规则见 [AGENTS.md](AGENTS.md)。
当前目录已改名，新公开仓已创建；Go module、release 配置和消费方下载入口尚未切换。

## 开发与检查

本仓根即 Go 模块根，版本以 `go.mod` 为准。已有代码检查入口：

```bash
./tools/ci-quality
```

消费方固定 release 和 SHA256，先显式运行 `tools/agent-doctor-bootstrap`，再执行
`tools/agent-doctor fix` / `check`。新 Nexa release 尚未发布，当前消费方继续使用固定上游版本。
换 release 必须同步版本与校验和，不能只替换下载 URL。

`check` 保持只读、离线和确定性；`fix` 只更新生成索引及适配器；bootstrap 负责下载与校验。
检查输出 `CONSISTENT` 只表示声明与工作区一致，不表示产品功能或运行验收完成。
