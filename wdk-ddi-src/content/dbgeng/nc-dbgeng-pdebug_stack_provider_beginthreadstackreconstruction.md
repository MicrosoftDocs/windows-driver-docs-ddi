---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION
title: PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION (dbgeng.h)
description: The BeginThreadStackReconstruction callback function causes debugger to pass the stream to the dump stack provider prior to thread enumeration.
old-location: debugger\beginthreadstackreconstruction.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION callback function"]
ms.keywords: BeginThreadStackReconstruction, BeginThreadStackReconstruction callback function [Windows Debugging], PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION, PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION callback, dbgeng/BeginThreadStackReconstruction, debugger.beginthreadstackreconstruction
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
 - PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION
 - dbgeng/PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Dbgeng.h
api_name:
 - BeginThreadStackReconstruction
---

# PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION callback function


## -description

The <i>BeginThreadStackReconstruction</i> callback function causes debugger to pass the stream to the dump stack provider prior to thread enumeration.

```cpp
CALLBACK* PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION BeginThreadStackReconstruction; 
```


## -parameters

### -param StreamType 

[in]
A stream type.

### -param MiniDumpStreamBuffer 

[in]
A mini-dump stream buffer.

### -param BufferSize 

[in]
The size of the buffer.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

<i>BeginThreadStackReconstruction</i> is called <b>PDEBUG_STACK_PROVIDER_BEGINTHREADSTACKRECONSTRUCTION</b> in the Dbgeng.h header file.

