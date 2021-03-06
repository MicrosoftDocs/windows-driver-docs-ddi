---
UID: NF:wiamdef.wiasDebugError
title: wiasDebugError function (wiamdef.h)
description: The wiasDebugError function is obsolete.
old-location: image\wiasdebugerror.htm
tech.root: image
ms.date: 11/18/2019
keywords: ["wiasDebugError function"]
ms.keywords: image.wiasdebugerror, wiamdef/wiasDebugError, wiasDebugError, wiasDebugError function [Imaging Devices], wiasFncs_0ccba388-a6ca-42b9-acd5-720b6763a202.xml
req.header: wiamdef.h
req.include-header: Wiamdef.h
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasDebugError
 - wiamdef/wiasDebugError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasDebugError
---

# wiasDebugError function


## -description

The **wiasDebugError** function is obsolete.

Use the [WIAS_ERROR](./nf-wiamdef-wias_error.md) macro instead.

**wiasDebugError** prints a debug error string in the Device Manager debug console. The output color is always red.

## -parameters

### -param hInstance

The handle of calling module.

### -param pszFormat

### -param ...

####### - pszFormat, ...

Specifies a variable argument list, which starts with an ANSI format string containing the message and any format specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

## -see-also

[WIAS_ERROR](./nf-wiamdef-wias_error.md)

[WIAS_LERROR](./nf-wiamdef-wias_lerror.md)

