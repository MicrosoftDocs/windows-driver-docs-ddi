---
UID: NF:wiamdef.wiasDebugTrace
title: wiasDebugTrace function (wiamdef.h)
description: The wiasDebugTrace function is obsolete.
old-location: image\wiasdebugtrace.htm
tech.root: image
ms.date: 11/18/2019
keywords: ["wiasDebugTrace function"]
ms.keywords: image.wiasdebugtrace, wiamdef/wiasDebugTrace, wiasDebugTrace, wiasDebugTrace function [Imaging Devices], wiasFncs_b6582555-3674-4261-a542-9a6388649bb0.xml
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
 - wiasDebugTrace
 - wiamdef/wiasDebugTrace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasDebugTrace
---

# wiasDebugTrace function


## -description

The **wiasDebugTrace** function is obsolete. Use the [WIAS_TRACE](./nf-wiamdef-wias_trace.md) macro instead.

This function prints a debug trace string in the Device Manager debug console.

## -parameters

### -param hInstance

Te handle of calling module.

### -param pszFormat

### -param param

####### - pszFormat, ...

Specifies a variable argument list, which starts with an ANSI format string containing the message and any format specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

## -remarks

To enable tracing in free builds, drivers must define the WIAS_DEBUG macro. Tracing is enabled by default in checked and debug builds of the operating system.

## -see-also

[WIAS_LTRACE](./nf-wiamdef-wias_ltrace.md)

[WIAS_TRACE](./nf-wiamdef-wias_trace.md)
