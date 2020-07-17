---
UID: NE:dbgmodel.VarArgsKind
title: VarArgsKind (dbgmodel.h)
description: Defines the style of variable arguments that a function definition takes.
ms.assetid: a3779feb-72c5-443a-ba30-dabb7fcd2e5d
ms.date: 07/16/2018
keywords: ["VarArgsKind enumeration"]
f1_keywords:
 - "dbgmodel/VarArgsKind"
 - "VarArgsKind"
ms.keywords: VarArgsKind, , 
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
- apiref
api_type: 
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- VarArgsKind
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# VarArgsKind enumeration

## -description

Defines the style of variable arguments that a function definition takes.

## -enum-fields

### -field VarArgsNone 
The function does not take any variable arguments.

### -field VarArgsCStyle 
The function is a C-style varargs function (returnType(arg1, arg2, ...)). The number of arguments reported by the function does not include the ellipsis argument. Any variable argument passing occurs after the number of arguments returned by the GetFunctionParameterTypeCount method.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
