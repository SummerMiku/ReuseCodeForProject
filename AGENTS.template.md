# <项目名> 仓库协作规则

## 范围与授权

- 阅读`docs/Workflow.md`、当前状态、目标票据和相关设计/源码后实施。
- 一次处理一张票据或用户明确批准的阶段；新票据先起草供审核。
- 已批准的票据和执行授权持续有效，必要的范围内步骤无需反复确认。
- 不把未知的数据库、接口或平台行为当事实；先查代码/协议或设计验证步骤。
- 不顺带实现未来票据、无关重构或大范围格式化；新发现写入后续问题。

## 架构与数据

- 实际架构依据：`ARCHITECTURE.md`；关键依赖方向：<填写>。
- 核心数据一致性约束：<事务/幂等/迁移/时间规则>。
- UI、外部服务和AI输入不能绕过客户端/服务端规定的校验入口。
- 数据升级保留原数据；不得用破坏性迁移或清库代替修复。

## 验证与交付

- 运行与本次变化有关的测试、构建和静态检查，命令从当前状态文件读取。
- 系统/网络/硬件/部署行为在相应真实环境验证；未执行项明确记录。
- 保存测试对应的源码commit和未提交差异；区分代码完成、用户验收、main集成和运行版本。
- 合并前审查完整差异和PR目标分支；合并后核对main源码，从该基线构建/交付。
- 真实用户数据默认保留；测试使用隔离数据和环境。

## Git与文档

- 保持main可构建；优先一票一分支，必要时使用独立worktree。
- 不reset、clean、强推、删除工作树或覆盖他人改动，除非用户明确要求。
- 不提交密钥、签名材料、个人数据库、日志和IDE状态。
- checkpoint时更新票据context/tasks；验收/合并/交付后同步Tickets、Current_State和报告。
- 关键决定写入`docs/decisions/`，记录原因、替代方案和影响。

## 完成报告

```text
Ticket/phase:
Summary:
Files changed:
Commands run:
Build/test results:
Manual verification:
Assumptions validated:
Risks:
Follow-up tickets:
Documentation updated:
Commit/PR/main/runtime versions:
```
