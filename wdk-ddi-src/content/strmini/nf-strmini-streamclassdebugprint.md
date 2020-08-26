---
UID: NF:strmini.StreamClassDebugPrint
title: StreamClassDebugPrint function (strmini.h)
description: This function is obsolete.
old-location: stream\streamclassdebugprint.htm
tech.root: stream
ms.assetid: a8b7efd2-7773-44dc-92de-85b03c31ada8
ms.date: 04/23/2018
keywords: ["StreamClassDebugPrint function"]
ms.keywords: StreamClassDebugPrint, StreamClassDebugPrint routine [Streaming Media Devices], strclass-routines_858a2dd4-ee74-44de-9293-05bd804c315d.xml, stream.streamclassdebugprint, strmini/StreamClassDebugPrint
f1_keywords:
 - "strmini/StreamClassDebugPrint"
 - "StreamClassDebugPrint"
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassDebugPrint
targetos: Windows
req.typenames: 
---

# StreamClassDebugPrint function

## -description

> [!NOTE]
> This function is obsolete.
>
> Checked builds were available on older versions of Windows, before Windows 10 version 1803. Use tools such as Driver Verifier and GFlags to check driver code in later versions of Windows.

## -parameters

### -param DebugPrintLevel 
[in]
Specifies an enumeration of type **STREAM_DEBUG_LEVEL**. The debugger prints messages if this parameter is less than or equal to the *StreamDebug* variable in *stream.sys* symbols.

### -param DebugMessage 
[in]
Points to a NULL-terminated string containing the message to print to the application window and to the Debugger Command window.

### -param param

#### - arguments

Specifies a variable argument list containing optional arguments for the format string, as in **printf**.

## -remarks

## -see-also
