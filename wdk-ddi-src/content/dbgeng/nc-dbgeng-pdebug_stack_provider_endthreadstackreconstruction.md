---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION
title: PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION (dbgeng.h)
description: The EndThreadStackReconstruction callback function may be called after stack reconstruction to clean up state.
old-location: debugger\endthreadstackreconstruction.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION callback function"]
ms.keywords: EndThreadStackReconstruction, EndThreadStackReconstruction callback function [Windows Debugging], PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION, PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION callback, dbgeng/EndThreadStackReconstruction, debugger.endthreadstackreconstruction
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
 - PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION
 - dbgeng/PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Dbgeng.h
api_name:
 - EndThreadStackReconstruction
---

# PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION callback function


## -description

The <i>EndThreadStackReconstruction</i> callback function may be called after stack reconstruction to clean up state.

```cpp
 CALLBACK* PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION EndThreadStackReconstruction;
```


## -parameters

### -param Arg1

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

<i>EndThreadStackReconstruction</i> is called <b>PDEBUG_STACK_PROVIDER_ENDTHREADSTACKRECONSTRUCTION</b> in the Dbgeng.h header file.

