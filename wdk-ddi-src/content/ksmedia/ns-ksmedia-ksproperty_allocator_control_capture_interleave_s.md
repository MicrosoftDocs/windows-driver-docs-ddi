---
UID: NS:ksmedia.KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
title: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
author: windows-driver-content
description: The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure specifies if interleaved capture is possible.
old-location: stream\ksproperty_allocator_control_capture_interleave_s.htm
old-project: stream
ms.assetid: e3885241-c6a4-417f-a7cf-38d221307f8e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, ,, A, C, E, I, K, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure [Streaming Media Devices], L, N, O, P, PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure pointer [Streaming Media Devices], R, S, T, U, V, Y, _, ksmedia/KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, ksmedia/PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, stream.ksproperty_allocator_control_capture_interleave_s, vidcapstruct_d012cbc9-457f-4689-943a-5dcf5eb33c46.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure


## -description


The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure specifies if interleaved capture is possible.


## -syntax


````
typedef struct {
  ULONG InterleavedCapPossible;
} KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S;
````


## -struct-fields




### -field InterleavedCapPossible

Indicates whether interleaved capture is possible. Any nonzero value indicates that interleaved capture is possible. A value of zero indicates interleaved capture is not possible.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564271">KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567792">PROPSETID_ALLOCATOR_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

