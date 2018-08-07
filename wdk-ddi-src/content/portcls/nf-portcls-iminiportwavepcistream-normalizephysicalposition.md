---
UID: NF:portcls.IMiniportWavePciStream.NormalizePhysicalPosition
title: IMiniportWavePciStream::NormalizePhysicalPosition
author: windows-driver-content
description: The NormalizePhysicalPosition method converts a physical buffer position to a time-based value.
old-location: audio\iminiportwavepcistream_normalizephysicalposition.htm
tech.root: audio
ms.assetid: 4ae4dc8d-3502-40c1-8109-6935990a7091
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IMiniportWavePciStream interface [Audio Devices],NormalizePhysicalPosition method, IMiniportWavePciStream.NormalizePhysicalPosition, IMiniportWavePciStream::NormalizePhysicalPosition, NormalizePhysicalPosition, NormalizePhysicalPosition method [Audio Devices], NormalizePhysicalPosition method [Audio Devices],IMiniportWavePciStream interface, audio.iminiportwavepcistream_normalizephysicalposition, audmp-routines_337339ea-4683-4b67-813c-a86e7e43597a.xml, portcls/IMiniportWavePciStream::NormalizePhysicalPosition
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
-	IMiniportWavePciStream.NormalizePhysicalPosition
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::NormalizePhysicalPosition


## -description


The <code>NormalizePhysicalPosition</code> method converts a physical buffer position to a time-based value.


## -parameters




### -param PhysicalPosition [in, out]

Pointer to a caller-allocated buffer that contains either the physical position or time-based value. On entry, this buffer contains the physical-position value that is to be converted. On return, the buffer contains the converted value, which is time-based.


## -returns



<code>NormalizePhysicalPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Given a physical position based on the actual number of bytes transferred, the <code>NormalizePhysicalPosition</code> method converts the position to a time-based value that is expressed in 100-nanosecond units.



