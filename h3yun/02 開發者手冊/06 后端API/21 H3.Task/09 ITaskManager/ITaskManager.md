---
title: "ITaskManager"
source: "https://help.h3yun.com/contents/644/772.html"
category: "開發者手冊 / 后端API / H3.Task / ITaskManager"
updated: 2025-12-21
tags:
  - h3yun
  - 開發者手冊
---
类名 : ITaskManager
说明 : 任务管理器 
方法名称 : AddTask(H3.Task.UserTask)

| 参数 | 说明 |
| --- | --- |
| "task" | 任务信息 |
| 返回值 |  |
| |  |


方法名称 : ActivateTask(System.String)

| 参数 | 说明 |
| --- | --- |
| "taskId" | 要激活的任务的任务Id |
| 返回值 |  |
| |  |


方法名称 : AddTasks(H3.Task.UserTask\[\])

| 参数 | 说明 |
| --- | --- |
| "tasks" | 添加的多个任务 |
| 返回值 |  |
| |  |


方法名称 : UpdateTask(H3.Task.UserTask)

| 参数 | 说明 |
| --- | --- |
| "task" | 要更新的任务 |
| 返回值 |  |
| |  |


方法名称 : GetTask(System.String)

| 参数 | 说明 |
| --- | --- |
| "taskId" | 任务的Id |
| 返回值 |  |
| 获得的任务 |  |


方法名称 : RemoveTaskById(System.String)

| 参数 | 说明 |
| --- | --- |
| "taskId" | 任务的Id |
| 返回值 |  |
| 如果删除成功则返回true，否则返回false |  |


方法名称 : RemoveTask(H3.Task.UserTask)

| 参数 | 说明 |
| --- | --- |
| "task" | 任务的 |
| 返回值 |  |
| 如果删除成功则返回true，否则返回false |  |


方法名称 : RemoveTasksByRuleId(System.String)

| 参数 | 说明 |
| --- | --- |
| "ruleId" | 规则Id |
| 返回值 |  |
| |  |


方法名称 : FinishTaskByTarget(System.String)

| 参数 | 说明 |
| --- | --- |
| "targetId" | 对象的Id |
| 返回值 |  |
| |  |


方法名称 : RemoveTasksByTargets(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "targetIds" | 对象的Id |
| 返回值 |  |
| |  |


方法名称 : AddTaskRule(H3.Task.UserTaskRule)

| 参数 | 说明 |
| --- | --- |
| "rule" | |
| 返回值 |  |
| |  |


方法名称 : RemoveTaskRule(System.String)

| 参数 | 说明 |
| --- | --- |
| "ruleId" | |
| 返回值 |  |
| |  |


方法名称 : UpdateTaskRule(H3.Task.UserTaskRule)

| 参数 | 说明 |
| --- | --- |
| "rule" | |
| 返回值 |  |
| |  |


方法名称 : GetTaskRules(System.String)

| 参数 | 说明 |
| --- | --- |
| "schemaCode" | |
| 返回值 |  |
| |  |


方法名称 : GetTaskRule(System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "scheduleId" | |
| "clone" | 是否克隆 |
| 返回值 |  |
| |
 |