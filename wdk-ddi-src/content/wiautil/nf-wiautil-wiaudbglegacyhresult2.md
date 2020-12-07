---
UID: NF:wiautil.wiauDbgLegacyHresult2
title: wiauDbgLegacyHresult2 function (wiautil.h)
description: The wiauDbgLegacyHresult2 function logs a default message containing an HRESULT.
old-location: image\wiaudbglegacyhresult2.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiauDbgLegacyHresult2 function"]
ms.keywords: image.wiaudbglegacyhresult2, wiauDbgLegacyHresult2, wiauDbgLegacyHresult2 function [Imaging Devices], wiauFncs_b980cd55-047b-4870-9bad-928253d0ce77.xml, wiautil/wiauDbgLegacyHresult2
req.header: wiautil.h
req.include-header: Wiautil.h
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
 - wiauDbgLegacyHresult2
 - wiautil/wiauDbgLegacyHresult2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiautil.h
api_name:
 - wiauDbgLegacyHresult2
---

# wiauDbgLegacyHresult2 function


## -description

The **wiauDbgLegacyHresult2** function logs a default message containing an HRESULT.

## -parameters

### -param hInstance 

[in]
Specifies the handle to the DLL instance.

### -param hr

Specifies the HRESULT to be logged.

## -remarks

A call to the **wiauDbgLegacyHresult2** function is equivalent to the following call to the [wiauDbgErrorHr](./nf-wiautil-wiaudbgerrorhr.md) function:

```cpp
wiauDbgErrorHr(hr, "", "");
```

That is, only one line is output to the log file and/or debugger. The line has the following form:

```cpp
ERROR HRESULT = HRESULT value, Error text for HRESULT
```

## -see-also

[wiauDbgErrorHr](./nf-wiautil-wiaudbgerrorhr.md)
