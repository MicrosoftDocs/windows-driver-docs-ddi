---
UID: NF:portcls.IMiniportWaveCyclicStream.NormalizePhysicalPosition
title: IMiniportWaveCyclicStream::NormalizePhysicalPosition method
author: windows-driver-content
description: The NormalizePhysicalPosition method converts a physical buffer position to a time-based value.
old-location: audio\iminiportwavecyclicstream_normalizephysicalposition.htm
old-project: audio
ms.assetid: 554cad50-d952-4658-904b-b2a8a8f75b76
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportWaveCyclicStream, IMiniportWaveCyclicStream::NormalizePhysicalPosition, NormalizePhysicalPosition
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportWaveCyclicStream.NormalizePhysicalPosition
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveCyclicStream::NormalizePhysicalPosition method



## -description
The <code>NormalizePhysicalPosition</code> method converts a physical buffer position to a time-based value.



## -syntax

````
NTSTATUS NormalizePhysicalPosition(
  [in, out] PLONGLONG PhysicalPosition
);
````


## -parameters

### -param PhysicalPosition [in, out]

Pointer to a caller-allocated variable that contains either the physical position or the time-based value. On entry, this buffer contains the physical-position value to convert. On return, the buffer contains the converted value, which is time-based.


## -returns
<code>NormalizePhysicalPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
<i>PhysicalPosition</i> is both an input and an output parameter. Given a physical position based on the actual number of bytes transferred, <code>NormalizePhysicalPosition</code> converts the position to a time-based value of 100-nanosecond units.</p>