---
UID: NA:wudfworkitem
ms.assetid: b0849fe5-c069-3886-b610-5c1f0eed6276
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wudfworkitem.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wudfworkitem.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WUDF_WORKITEM_CONFIG_INIT function](nf-wudfworkitem-wudf_workitem_config_init.md) | The WUDF_WORKITEM_CONFIG_INIT macro initializes a driver's WUDF_WORKITEM_CONFIG structure. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [WUDF_WORKITEM_FUNCTION callback](nc-wudfworkitem-wudf_workitem_function.md) | A driver's OnWorkItem event callback function performs the work that is associated with a specified work item. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WUDF_WORKITEM_CONFIG structure](ns-wudfworkitem-_wudf_workitem_config.md) | The WUDF_WORKITEM_CONFIG structure contains information that is associated with a work item. |
