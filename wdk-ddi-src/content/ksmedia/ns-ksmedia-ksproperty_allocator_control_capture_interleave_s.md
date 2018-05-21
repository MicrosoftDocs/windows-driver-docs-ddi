---
UID: NS:ksmedia.KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
title: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
author: windows-driver-content
description: The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure specifies if interleaved capture is possible.
old-location: stream\ksproperty_allocator_control_capture_interleave_s.htm
old-project: stream
ms.assetid: e3885241-c6a4-417f-a7cf-38d221307f8e
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure [Streaming Media Devices], PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, ksmedia/PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, stream.ksproperty_allocator_control_capture_interleave_s, vidcapstruct_d012cbc9-457f-4689-943a-5dcf5eb33c46.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure


## -description


The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure specifies if interleaved capture is possible.


## -struct-fields




### -field InterleavedCapPossible

Indicates whether interleaved capture is possible. Any nonzero value indicates that interleaved capture is possible. A value of zero indicates interleaved capture is not possible.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564271">KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567792">PROPSETID_ALLOCATOR_CONTROL</a>
 

 

