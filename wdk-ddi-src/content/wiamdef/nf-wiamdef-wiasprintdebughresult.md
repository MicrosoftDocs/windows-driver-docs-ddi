---
UID: NF:wiamdef.wiasPrintDebugHResult
title: wiasPrintDebugHResult function (wiamdef.h)
description: The wiasPrintDebugHResult function is obsolete.
old-location: image\wiasprintdebughresult.htm
tech.root: image
ms.assetid: f9dc5379-0efa-4743-9460-bfb16945768b
ms.date: 11/18/2019
keywords: ["wiasPrintDebugHResult function"]
ms.keywords: image.wiasprintdebughresult, wiamdef/wiasPrintDebugHResult, wiasFncs_932e688a-da37-4a53-91ff-f0c0abca4f98.xml, wiasPrintDebugHResult, wiasPrintDebugHResult function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasPrintDebugHResult"
 - "wiasPrintDebugHResult"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasPrintDebugHResult
targetos: Windows
req.typenames: 
---

# wiasPrintDebugHResult function

## -description

The **wiasPrintDebugHResult** function is obsolete for Windows XP and later, and is no longer supported. Use the [WIAS_LHRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_lhresult) macro instead.

This function prints an HRESULT string on the Device Manager debug console.

## -parameters

### -param hInstance

The handle of the calling module.

### -param hr

Specifies the HRESULT to be printed.

## -see-also

[WIAS_LHRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_lhresult)
