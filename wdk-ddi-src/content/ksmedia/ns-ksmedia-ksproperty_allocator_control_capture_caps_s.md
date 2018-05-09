---
UID: NS:ksmedia.KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
title: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
author: windows-driver-content
description: The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported.
old-location: stream\ksproperty_allocator_control_capture_caps_s.htm
old-project: stream
ms.assetid: be13bf95-eae9-4ae4-b5f3-cc1bdf3acd02
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, ksmedia/PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, stream.ksproperty_allocator_control_capture_caps_s, vidcapstruct_705f4e1a-dc90-446d-bf3c-97fe454db939.xml"
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
-	KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure


## -description


The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported.


## -struct-fields




### -field InterleavedCapSupported

Indicates whether interleaved capture is supported. Any nonzero value indicates that interleaved capture is supported. A value of zero indicates interleaved capture is not supported.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564267">KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567792">PROPSETID_ALLOCATOR_CONTROL</a>
 

 

