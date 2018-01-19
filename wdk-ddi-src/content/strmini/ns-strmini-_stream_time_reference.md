---
UID: NS:strmini._STREAM_TIME_REFERENCE
title: _STREAM_TIME_REFERENCE
author: windows-driver-content
description: .
old-location: stream\stream_time_reference.htm
old-project: stream
ms.assetid: BC3839C0-AED6-470D-9C2B-B1529B2B3D1A
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _STREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_TIME_REFERENCE
req.alt-loc: Strmini.h
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
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# _STREAM_TIME_REFERENCE structure



## -description




## -syntax

````
typedef struct _STREAM_TIME_REFERENCE {
  STREAM_TIMESTAMP CurrentOnboardClockValue;
  LARGE_INTEGER    OnboardClockFrequency;
  LARGE_INTEGER    CurrentSystemTime;
  ULONG            Reserved[2];
} STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE;
````


## -struct-fields

### -field CurrentOnboardClockValue

Current value of the adapter clock.


### -field OnboardClockFrequency

Frequency of the adapter clock.


### -field CurrentSystemTime

KeQueryPerformanceCounter time.


### -field Reserved

Reserved for future use.


## -remarks
