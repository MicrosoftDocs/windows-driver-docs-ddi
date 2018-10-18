---
UID: NF:portcls.IMiniportWaveCyclicStream.NormalizePhysicalPosition
title: IMiniportWaveCyclicStream::NormalizePhysicalPosition
author: windows-driver-content
description: The NormalizePhysicalPosition method converts a physical buffer position to a time-based value.
old-location: audio\iminiportwavecyclicstream_normalizephysicalposition.htm
tech.root: audio
ms.assetid: 554cad50-d952-4658-904b-b2a8a8f75b76
ms.date: 5/8/2018
ms.keywords: IMiniportWaveCyclicStream interface [Audio Devices],NormalizePhysicalPosition method, IMiniportWaveCyclicStream.NormalizePhysicalPosition, IMiniportWaveCyclicStream::NormalizePhysicalPosition, NormalizePhysicalPosition, NormalizePhysicalPosition method [Audio Devices], NormalizePhysicalPosition method [Audio Devices],IMiniportWaveCyclicStream interface, audio.iminiportwavecyclicstream_normalizephysicalposition, audmp-routines_a1b6d530-8199-4c5d-87ee-8f00d60436b0.xml, portcls/IMiniportWaveCyclicStream::NormalizePhysicalPosition
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveCyclicStream.NormalizePhysicalPosition
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclicStream::NormalizePhysicalPosition


## -description


The <code>NormalizePhysicalPosition</code> method converts a physical buffer position to a time-based value.


## -parameters




### -param PhysicalPosition [in, out]

Pointer to a caller-allocated variable that contains either the physical position or the time-based value. On entry, this buffer contains the physical-position value to convert. On return, the buffer contains the converted value, which is time-based.


## -returns



<code>NormalizePhysicalPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



<i>PhysicalPosition</i> is both an input and an output parameter. Given a physical position based on the actual number of bytes transferred, <code>NormalizePhysicalPosition</code> converts the position to a time-based value of 100-nanosecond units.



