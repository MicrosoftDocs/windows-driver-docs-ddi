---
UID: NE:dbgmodel.CallingConventionKind
title: CallingConventionKind
description: Defines the kind of calling convention of a function type.
ms.assetid: c25b87e4-c917-4feb-94c7-9cffe4f4193e
ms.date: 10/05/2018
ms.topic: enum
ms.keywords: CallingConventionKind, , 
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
-	CallingConventionKind
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# CallingConventionKind enumeration

## -description

Defines the kind of calling convention of a function type.


## -enum-fields

### -field CallingConventionUnknown 

The calling convention is not known

### -field CallingConventionCDecl 

The calling convention is __cdecl


### -field CallingConventionFastCall 
The calling convention is fastcall
    

### -field CallingConventionStdCall 
The calling convention is stdcall
    

### -field CallingConventionSysCall 
The calling convention is syscall
    

### -field CallingConventionThisCall 
The calling convention is thiscall

## -remarks

## -see-also

[Debugger Data Model C++ Interfaces Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
