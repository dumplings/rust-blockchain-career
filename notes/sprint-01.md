# Sprint-01

## 目录、文件意义解读

- main.rs，binary crate入口，负责接收输入，调用业务能力，处理最终输出以及进程退出。
  - 负责编排
- lib.rs，用来定义crate对外提供什么能力。
  - crate public API

数据结构 应该比 业务逻辑 更稳定。
功能模块依赖数据模型。
