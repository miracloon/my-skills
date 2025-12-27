---
name: dev-subtask
description: Resolve taskXX markdown files under a given folder using task id(s)/range, then delegate to @doc-driven-dev-assistant with the matched file paths.
argument-hint: <task-docs-dir> <task-ids-or-range>
---

参数：
- `$1`：任务文档父目录（完整路径），例如：`/home/ry/code/hydro_datakit_dev/docs/dev_notes/ert_pseudo_build`
- `$2`：任务编号/范围（按用户意图理解即可），例如：`01`、`3-5`、`12`

动作：
- 在 `$1` 下找到与 `$2` 对应的 `taskXX*.md` 文件;
- 将该路径列表交给 `@doc-driven-dev-assistant` 执行;
- 若无法唯一定位：输出候选列表与缺失项，并停止等待用户指示。
