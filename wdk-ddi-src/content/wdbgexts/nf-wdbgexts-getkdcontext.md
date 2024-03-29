---
UID: NF:wdbgexts.GetKdContext
title: GetKdContext macro (wdbgexts.h)
description: The GetKdContext function returns the total number of processors and the number of the current processor in the structure ppi points to.
old-location: debugger\getkdcontext.htm
tech.root: debugger
ms.date: 07/27/2023
keywords: ["GetKdContext macro"]
ms.keywords: GetKdContext, GetKdContext function [Windows Debugging], WdbgExts_Ref_951ca10a-3a73-433c-bd95-f054967f0df6.xml, debugger.getkdcontext, wdbgexts/GetKdContext
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - GetKdContext
 - wdbgexts/GetKdContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - GetKdContext
---

# GetKdContext macro

## -description

The <b>GetKdContext</b> function returns the total number of processors and the number of the current processor in the structure <i>ppi</i> points to.

## -parameters

### -param ppi

Points to the following structure:

```cpp
typedef struct _PROCESSORINFO {
  USHORT  Processor;           // current processor
  USHORT  NumberProcessors;    // total number of processors
} PROCESSORINFO, *PPROCESSORINFO;
```

## -remarks

### Returns

The total number of processors in the structure.
