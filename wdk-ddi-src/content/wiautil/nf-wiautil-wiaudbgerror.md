---
UID: NF:wiautil.wiauDbgError
title: wiauDbgError function (wiautil.h)
description: The wiauDbgError function logs an error message.
old-location: image\wiaudbgerror.htm
tech.root: image
ms.assetid: 112d6f90-33b3-446b-943c-8995e6ec3378
ms.date: 05/03/2018
keywords: ["wiauDbgError function"]
ms.keywords: image.wiaudbgerror, wiauDbgError, wiauDbgError function [Imaging Devices], wiauFncs_73184286-df53-4272-9fa8-aae1d1fb3dbc.xml, wiautil/wiauDbgError
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
 - wiauDbgError
 - wiautil/wiauDbgError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wiautil.h
api_name:
 - wiauDbgError
---

# wiauDbgError function


## -description

The **wiauDbgError** function logs an error message.

## -parameters

### -param fname

Pointer to a string containing the name of the function or method into which the call to **wiauDbgDump** is inserted.

### -param fmt

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

### -param param

####### - fmt, ...

## -remarks

The **wiauDbgError** typically is used to display an error message with no data, such as in the following example:

```cpp
wiauDbgError("Read", "Attempting to read past end of buffer");
```

## -see-also

[wiauDbgDump](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgdump)

[wiauDbgErrorHr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerrorhr)

[wiauDbgTrace](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgtrace)

[wiauDbgWarning](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgwarning)

