---
UID: NF:wiautil.wiauDbgWarning
title: wiauDbgWarning function (wiautil.h)
description: The wiauDbgWarning function logs a warning message.
old-location: image\wiaudbgwarning.htm
tech.root: image
ms.assetid: f10f1c28-0bfd-44c5-a0aa-9f9227f775d2
ms.date: 05/03/2018
keywords: ["wiauDbgWarning function"]
ms.keywords: image.wiaudbgwarning, wiauDbgWarning, wiauDbgWarning function [Imaging Devices], wiauFncs_1248626b-0d4f-445c-855c-9ba477cf306c.xml, wiautil/wiauDbgWarning
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
 - wiauDbgWarning
 - wiautil/wiauDbgWarning
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wiautil.h
api_name:
 - wiauDbgWarning
---

# wiauDbgWarning function


## -description

The <b>wiauDbgWarning</b> function logs a warning message.

## -parameters

### -param fname

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgWarning</b> is inserted.

### -param fmt

### -param param

####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the warning message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgdump">wiauDbgDump</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerror">wiauDbgError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerrorhr">wiauDbgErrorHr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgtrace">wiauDbgTrace</a>

