---
title: "跨应用JS API"
source: "https://docs.aliwork.com/docs/yida_support/lbtl0t/ocmxyv/fktkelqgtugmusls"
category: "用戶手冊 / 开发者功能（需有代码基础） / JS 动作面板 - 前端代码开发"
updated: 
tags:
  - yida
  - 用戶手冊
---
调用方式为`this.utils.yida.<函数名>`。

## 表单操作类API

| **函数名称** | **描述** | **请求示例** |
| --- | --- | --- |
| **saveFormData** | 新建表单实例 |
```javascript
// 新建表单实例this.utils.yida.saveFormData({formUuid:'FORM-xxx',appType: pageConfig.appType,formDataJson:JSON.stringify({textField_m1g4dcpy:'单行文本',textareaField_m1g4dcpz:'多行文本',}),}).then((res)=>{console.log('新建结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **updateFormData** | 更新表单中指定组件值 |

```javascript
// 更新表单中指定组件值this.utils.yida.updateFormData({formInstId:'FINST-xxx',updateFormDataJson:JSON.stringify({textField_m1g4dcpy:'单行文本',textareaField_m1g4dcpz:'多行文本',}),useLatestVersion:'y',}).then((res)=>{console.log('更新成功');}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **searchFormDataIds** | 根据条件搜索表单实例 ID 列表 |

```javascript
// 根据条件搜索表单实例 ID 列表this.utils.yida.searchFormDataIds({formUuid:'FORM-xxx',currentPage:1,pageSize:10,searchFieldJson:JSON.stringify({textField_m1g4dcpy:'单行文本',textareaField_m1g4dcpz:'多行文本',}),}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **getFormComponentDefinationList** | 获取表单定义 |

```javascript
// 获取表单定义this.utils.yida.getFormComponentDefinationList({formUuid:'FORM-xxx',version:'',}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **deleteFormData** | 删除表单实例 |

```javascript
// 删除表单实例this.utils.yida.deleteFormData({formUuid:'FORM-xxx',}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **getFormDataById** | 根据表单实例 ID 查询表单实例详情 |

```javascript
// 根据表单实例 ID 查询表单实例详情this.utils.yida.getFormDataById({formInstId:'FINST-xxxx',}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **searchFormDatas** | 根据条件搜索表单实例详情列表 |

```javascript
// 根据条件搜索表单示例详情列表this.utils.yida.searchFormDatas({formUuid:'FORM-xxx',searchFieldJson:'',// 根据表单内组件值查询currentPage:'1',pageSize:'10',originatorId:'',// 根据数据提交人工号查询createFrom:'2024-01-01',createTo:'2024-02-01',modifiedFrom:'2024-01-01',modifiedTo:'2024-02-01',dynamicOrder:'',// 排序}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |

## 流程操作类API

| **函数名称** | **描述** | **请求示例** |
| --- | --- | --- |
| **startInstance** | 流程发起 |
```javascript
// 流程发起this.utils.yida.startProcessInstance({formUuid:'FORM-xxx',processCode:'TPROC--xxx',deptId:'',formDataJson:JSON.stringify({textField_xxx:'单行文本',textareaField_xxx:'多行文本',}),}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **updateInstance** | 流程实例更新 |

```javascript
// 流程流程实例更新this.utils.yida.updateProcessInstance({processInstanceId:'f30233fb-xxx-9ee530',updateFormDataJson:JSON.stringify({textField_xxx:'单行文本',textareaField_xxx:'多行文本',}),}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **deleteInstance** | 删除流程实例 |

```javascript
// 删除流程实例this.utils.yida.deleteProcessInstance({processInstanceId:'f30233fb-xxx-9ee530',}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **getInstances** | 根据搜索条件获取实例详情列表 |

```javascript
// 根据搜索条件获取实例详情列表this.utils.yida.getProcessInstances({formUuid:'FORM-xxx',// 表单IDtaskId:'2199132092',// 任务IDinstanceStatus:'RUNNING',// 实例状态approvedResult:'agree',// 流程审批结果currentPage:'1',pageSize:'10',originatorId:'2134',// 根据流程发起人工号查询createFrom:'2024-01-01',createTo:'2024-02-01',modifiedFrom:'2024-01-01',modifiedTo:'2024-02-01',searchFieldJson:JSON.stringify({textField_xxx:'单行文本',textareaField_xxx:'多行文本',}),}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **getInstanceIds** | 根据条件搜索流程实例 ID |

```javascript
// 根据搜索条件获取实例ID列表this.utils.yida.getProcessInstanceIds({formUuid:'FORM-xxx',// 表单IDtaskId:'2199132092',// 任务IDinstanceStatus:'RUNNING',// 实例状态approvedResult:'agree',// 流程审批结果currentPage:'1',pageSize:'10',originatorId:'2134',// 根据流程发起人工号查询createFrom:'2024-01-01',createTo:'2024-02-01',modifiedFrom:'2024-01-01',modifiedTo:'2024-02-01',searchFieldJson:JSON.stringify({textField_xxx:'单行文本',textareaField_xxx:'多行文本',}),}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
| **getInstanceById** | 根据实例 ID 获取流程实例详情 |

```javascript
// 根据实例 ID 获取流程实例详情this.utils.yida.getProcessInstanceById({processInstanceId:'f30233fb-xxx-530',}).then((res)=>{console.log('请求结果', res);}).catch(({ message })=>{this.utils.toast({title: message,type:'error',});});
```

 |
