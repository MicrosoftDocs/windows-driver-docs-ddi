---
UID: NF:wiautil.wiauDbgDump
title: wiauDbgDump function (wiautil.h)
description: The wiauDbgDump function logs a message containing one or more data values.
tech.root: image
ms.date: 04/20/2022
keywords: ["wiauDbgDump function"]
ms.keywords: image.wiaudbgdump, wiauDbgDump, wiauDbgDump function [Imaging Devices], wiauFncs_dbe56add-64ef-442d-9824-ed0b26aba9ac.xml, wiautil/wiauDbgDump
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
 - wiauDbgDump
 - wiautil/wiauDbgDump
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wiautil.h
api_name:
 - wiauDbgDump
---

## -description

The **wiauDbgDump** function logs a message containing one or more data values.

## -parameters

### -param fname

Pointer to a string containing the name of the function or method into which the call to **wiauDbgDump** is inserted.

### -param fmt

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

### -param ...

## -remarks

The **wiauDbgDump** function typically is used to log a message along with one or more data values, as in the following example:

```cpp
wiauDbgDump("SetBuffer", "Buffer size set to %d bytes.", size);
```

This example, which would be placed in a function named *SetBuffer*, causes the function name and a string describing the size of a buffer to be logged.

## -see-also

[wiauDbgError](./nf-wiautil-wiaudbgerror.md)

[wiauDbgErrorHr](./nf-wiautil-wiaudbgerrorhr.md)

[wiauDbgTrace](./nf-wiautil-wiaudbgtrace.md)

[wiauDbgWarning](./nf-wiautil-wiaudbgwarning.md)
