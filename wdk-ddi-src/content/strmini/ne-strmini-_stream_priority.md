---
UID: NE:strmini._STREAM_PRIORITY
title: _STREAM_PRIORITY
author: windows-driver-content
description: TD.
old-location: stream\stream_priority.htm
old-project: stream
ms.assetid: 790A00A5-1107-4686-B690-80D07B69AF62
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: LowToHigh, *PSTREAM_PRIORITY, Low, PSTREAM_PRIORITY, strmini/Low, strmini/LowToHigh, STREAM_PRIORITY, stream.stream_priority, PSTREAM_PRIORITY enumeration pointer [Streaming Media Devices], strmini/PSTREAM_PRIORITY, strmini/STREAM_PRIORITY, STREAM_PRIORITY enumeration [Streaming Media Devices], Dispatch, High, _STREAM_PRIORITY, strmini/High, strmini/Dispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
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
req.lib: 
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Strmini.h
apiname: 
-	STREAM_PRIORITY
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# _STREAM_PRIORITY enumeration


## -description


TD


## -syntax


````
typedef enum _STREAM_PRIORITY { 
  High,
  Dispatch,
  Low,
  LowToHigh                   
} STREAM_PRIORITY, *PSTREAM_PRIORITY
;
````


## -enum-fields




### -field High

Highest priority, IRQL equal to the adapter's ISR.


### -field Dispatch

Medium priority, IRQL equal to dispatch level.


### -field Low

Lowest priority, IRQL equal to passive or APC level.


### -field LowToHigh

Go from low priority to high priority.

