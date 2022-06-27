---
UID: NF:wiautil.wiauDbgErrorHr
title: wiauDbgErrorHr function (wiautil.h)
description: The wiauDbgErrorHr function logs a message containing an HRESULT and its error message string.
tech.root: image
ms.date: 04/20/2022
keywords: ["wiauDbgErrorHr function"]
ms.keywords: image.wiaudbgerrorhr, wiauDbgErrorHr, wiauDbgErrorHr function [Imaging Devices], wiauFncs_1400188e-53d1-481c-a470-8a2247b7f34f.xml, wiautil/wiauDbgErrorHr
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
 - wiauDbgErrorHr
 - wiautil/wiauDbgErrorHr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wiautil.h
api_name:
 - wiauDbgErrorHr
---

## -description

The **wiauDbgErrorHr** function logs a message containing an HRESULT and its error message string.

## -parameters

### -param hr

Specifies the HRESULT that is to be logged.

### -param fname

Pointer to a string containing the name of the function or method into which the call to **wiauDbgDump** is inserted.

### -param fmt

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

### -param ...

Additional parameters.

## -remarks

The **wiauDbgErrorHr** function typically logs two lines to the log file, or debugger, or both. The first line contains the text of the *fmt* parameter, including data, if provided. The second line contains the HRESULT and the message string associated with that HRESULT. The following example shows how this function might be called:

```cpp
wiauDbgErrorHr(hr, "AllocateBuffer", "Buffer size is %d bytes", size);
```

## -see-also

[wiauDbgDump](./nf-wiautil-wiaudbgdump.md)

[wiauDbgError](./nf-wiautil-wiaudbgerror.md)

[wiauDbgTrace](./nf-wiautil-wiaudbgtrace.md)

[wiauDbgWarning](./nf-wiautil-wiaudbgwarning.md)
