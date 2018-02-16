---
UID: NF:strmini.StreamClassRegisterAdapter
title: StreamClassRegisterAdapter function
author: windows-driver-content
description: The StreamClassRegisterAdapter routine registers a stream class minidriver.
old-location: stream\streamclassregisteradapter.htm
old-project: stream
ms.assetid: f57e9c0f-d99b-4b01-b512-4a8f754c8822
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: StreamClassRegisterAdapter function [Streaming Media Devices], strclass-routines_059c6a60-83c5-4eaa-ade5-f60ddcbba594.xml, StreamClassRegisterAdapter, strmini/StreamClassRegisterAdapter, stream.streamclassregisteradapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	strmini.h
apiname:
-	StreamClassRegisterAdapter
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassRegisterAdapter function


## -description


The <b>StreamClassRegisterAdapter</b> routine registers a stream class minidriver.

The name <b>StreamClassRegisterAdapter</b> is supported for backward compatibility only.

Instead, Microsoft recommends the use of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>, an alias of <b>StreamClassRegisterAdapter</b>. The name <b>StreamClassRegisterMinidriver</b> more accurately indicates that the routine registers a stream class minidriver. Once registered, a minidriver can drive any number of adapter instances in a system.


## -syntax


````
  StreamClassRegisterAdapter(
    
);
````


## -parameters




### -param Argument1

TBD


### -param Argument2

TBD


### -param HwInitializationData

TBD





