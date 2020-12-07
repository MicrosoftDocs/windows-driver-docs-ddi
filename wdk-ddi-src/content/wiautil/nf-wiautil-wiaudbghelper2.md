---
UID: NF:wiautil.wiauDbgHelper2
title: wiauDbgHelper2 function (wiautil.h)
description: The wiauDbgHelper2 function writes a message to a log file, or debugger, or both.
old-location: image\wiaudbghelper2.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiauDbgHelper2 function"]
ms.keywords: image.wiaudbghelper2, wiauDbgHelper2, wiauDbgHelper2 function [Imaging Devices], wiauFncs_6ccf146a-ec2e-4ca4-827a-dec2f8ea629d.xml, wiautil/wiauDbgHelper2
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
 - wiauDbgHelper2
 - wiautil/wiauDbgHelper2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wiautil.h
api_name:
 - wiauDbgHelper2
---

# wiauDbgHelper2 function


## -description

The **wiauDbgHelper2** function writes a message to a log file, or debugger, or both.

## -parameters

### -param prefix

Pointer to a string containing a prefix (such as "ERROR " or "WARN ") associated with the message.

### -param fname

Pointer to a string containing the name of the function or method into which the call to **wiauDbgHelper2** is inserted.

### -param fmt

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output. The text should be prefixed with the full name of the method or function generating the message in the format of "class::method, message-text".

### -param param

####### - fmt, ...

## -remarks

The **wiauDbgHelper2** function enables those using it to write **printf**-style messages, with variable argument lists, to a log file or debugger. The following example demonstrates how this function might be used:

```cpp
wiauDbgHelper2("ERROR", "MyFunc", "Buffer size too small - %d bytes", BufSize);
```

## -see-also

[wiauDbgDump](./nf-wiautil-wiaudbgdump.md)

[wiauDbgError](./nf-wiautil-wiaudbgerror.md)

[wiauDbgErrorHr](./nf-wiautil-wiaudbgerrorhr.md)

[wiauDbgHelper](./nf-wiautil-wiaudbghelper.md)

[wiauDbgTrace](./nf-wiautil-wiaudbgtrace.md)

[wiauDbgWarning](./nf-wiautil-wiaudbgwarning.md)
