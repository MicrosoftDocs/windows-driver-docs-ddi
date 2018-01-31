---
UID: NE:ks.KSPROPERTY_STREAM
title: KSPROPERTY_STREAM
author: windows-driver-content
description: "."
old-location: stream\ksproperty_stream.htm
old-project: stream
ms.assetid: 1A7C7181-00AF-4AAB-822F-017F11DB9409
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_STREAM_PRESENTATIONEXTENT, KSPROPERTY_STREAM_QUALITY, ks/KSPROPERTY_STREAM, ks/KSPROPERTY_STREAM_FRAMETIME, ks/KSPROPERTY_STREAM_ALLOCATOR, ks/KSPROPERTY_STREAM_RATE, ks/KSPROPERTY_STREAM_RATECAPABILITY, KSPROPERTY_STREAM_DEGRADATION, ks/KSPROPERTY_STREAM_DEGRADATION, KSPROPERTY_STREAM enumeration [Streaming Media Devices], KSPROPERTY_STREAM_RATE, KSPROPERTY_STREAM_FRAMETIME, KSPROPERTY_STREAM_TIMEFORMAT, ks/KSPROPERTY_STREAM_PRESENTATIONTIME, KSPROPERTY_STREAM_ALLOCATOR, KSPROPERTY_STREAM_MASTERCLOCK, ks/KSPROPERTY_STREAM_PRESENTATIONEXTENT, ks/KSPROPERTY_STREAM_TIMEFORMAT, ks/KSPROPERTY_STREAM_QUALITY, ks/KSPROPERTY_STREAM_MASTERCLOCK, KSPROPERTY_STREAM_PIPE_ID, stream.ksproperty_stream, KSPROPERTY_STREAM_PRESENTATIONTIME, ks/KSPROPERTY_STREAM_PIPE_ID, KSPROPERTY_STREAM, KSPROPERTY_STREAM_RATECAPABILITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
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
-	Ks.h
apiname:
-	KSPROPERTY_STREAM
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_STREAM
---

# KSPROPERTY_STREAM enumeration


## -description





## -syntax


````
typedef enum  { 
  KSPROPERTY_STREAM_ALLOCATOR,
  KSPROPERTY_STREAM_QUALITY,
  KSPROPERTY_STREAM_DEGRADATION,
  KSPROPERTY_STREAM_MASTERCLOCK,
  KSPROPERTY_STREAM_TIMEFORMAT,
  KSPROPERTY_STREAM_PRESENTATIONTIME,
  KSPROPERTY_STREAM_PRESENTATIONEXTENT,
  KSPROPERTY_STREAM_FRAMETIME,
  KSPROPERTY_STREAM_RATECAPABILITY,
  KSPROPERTY_STREAM_RATE,
  KSPROPERTY_STREAM_PIPE_ID
} KSPROPERTY_STREAM;
````


## -enum-fields




#### - KSPROPERTY_STREAM_ALLOCATOR

Specify if the pin allocates stream buffers or can provide an allocator.


#### - KSPROPERTY_STREAM_QUALITY

Specify if the pin generates Quality Management complaints.


#### - KSPROPERTY_STREAM_DEGRADATION

Specify if the pin allows degradation strategies.


#### - KSPROPERTY_STREAM_MASTERCLOCK

Specify if the pin uses or produces a master clock that can be used for synchronization.


#### - KSPROPERTY_STREAM_TIMEFORMAT

Specify to retrieve the time format used on a particular pin connection.


#### - KSPROPERTY_STREAM_PRESENTATIONTIME

Specify to retrieve and set the current presentation time of a filter pin.


#### - KSPROPERTY_STREAM_PRESENTATIONEXTENT

Specify to query the stream extent.


#### - KSPROPERTY_STREAM_FRAMETIME

Specify to determine the duration of the next frame based on the particular media stream, and use that information to step-frame a sequence.


#### - KSPROPERTY_STREAM_RATECAPABILITY

Specify to allow a graph manager to query all connection points involved in the flow of a particular stream (obtained through KSPROPERTY_PIN_DATAROUTING) for their capability in adjusting a requested rate to the nominal rate.


#### - KSPROPERTY_STREAM_RATE

Specify in conjunction with KSPROPERTY_STREAM_RATECAPABILITY and use this to set the rate of a segment after querying the capability of the pin.


#### - KSPROPERTY_STREAM_PIPE_ID

Used internally for communication between the KSProxy system driver and AVStream.

