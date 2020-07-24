---
UID: NF:wiautil.wiauDbgDump
title: wiauDbgDump function (wiautil.h)
description: The wiauDbgDump function logs a message containing one or more data values.
old-location: image\wiaudbgdump.htm
tech.root: image
ms.assetid: 5df074ff-572d-47f7-9c5c-4423b200cddc
ms.date: 05/03/2018
keywords: ["wiauDbgDump function"]
ms.keywords: image.wiaudbgdump, wiauDbgDump, wiauDbgDump function [Imaging Devices], wiauFncs_dbe56add-64ef-442d-9824-ed0b26aba9ac.xml, wiautil/wiauDbgDump
f1_keywords:
 - "wiautil/wiauDbgDump"
 - "wiauDbgDump"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wiautil.h
api_name:
- wiauDbgDump
targetos: Windows
req.typenames: 
---

# wiauDbgDump function

## -description

The **wiauDbgDump** function logs a message containing one or more data values.

## -parameters

### -param fname

Pointer to a string containing the name of the function or method into which the call to **wiauDbgDump** is inserted.

### -param fmt

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

### -param param

#### - fmt, ...

## -remarks

The **wiauDbgDump** function typically is used to log a message along with one or more data values, as in the following example:

```cpp
wiauDbgDump("SetBuffer", "Buffer size set to %d bytes.", size);
```

This example, which would be placed in a function named *SetBuffer*, causes the function name and a string describing the size of a buffer to be logged.

## -see-also

[wiauDbgError](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerror)

[wiauDbgErrorHr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerrorhr)

[wiauDbgTrace](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgtrace)

[wiauDbgWarning](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgwarning)
