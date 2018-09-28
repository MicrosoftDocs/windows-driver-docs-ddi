---
UID: NE:dbgmodel.ScriptExecutionKind
title: ScriptExecutionKind
author: windows-driver-content
description: 
ms.assetid: f39e999b-9d77-496b-841d-c89d13b776d3
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: ScriptExecutionKind, , 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	ScriptExecutionKind
product: Windows
targetos: Windows
tech.root: debugger
---

# ScriptExecutionKind enumeration

## -description

Defines the kind of execution to do.

## -enum-fields

### -field ScriptExecutionNormal 
Indicates that you would like the script to execute normally

### -field ScriptExecutionStepIn 
Indicates that you want to perform a "step in" operation

### -field ScriptExecutionStepOut 
Indicates that you want to perform a "step out" operation

### -field ScriptExecutionStepOver 
Indicates that you want to perform a "step over" operation

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
