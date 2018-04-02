---
UID: NE:ksmedia.CAPTURE_MEMORY_ALLOCATION_FLAGS
title: CAPTURE_MEMORY_ALLOCATION_FLAGS
author: windows-driver-content
description: The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data.
old-location: stream\capture_memory_allocation_flags.htm
old-project: stream
ms.assetid: 3b96301a-28a5-494b-bd12-8d3d4516730e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PCAPTURE_MEMORY_ALLOCATION_FLAGS, CAPTURE_MEMORY_ALLOCATION_FLAGS, CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration [Streaming Media Devices], KS_CAPTURE_ALLOC_INVALID, KS_CAPTURE_ALLOC_SYSTEM, KS_CAPTURE_ALLOC_SYSTEM_AGP, KS_CAPTURE_ALLOC_VRAM, KS_CAPTURE_ALLOC_VRAM_MAPPED, PCAPTURE_MEMORY_ALLOCATION_FLAGS, PCAPTURE_MEMORY_ALLOCATION_FLAGS enumeration pointer [Streaming Media Devices], avstruct_2c1411b2-f4a6-44f9-ba68-63f2f5654105.xml, ksmedia/CAPTURE_MEMORY_ALLOCATION_FLAGS, ksmedia/KS_CAPTURE_ALLOC_INVALID, ksmedia/KS_CAPTURE_ALLOC_SYSTEM, ksmedia/KS_CAPTURE_ALLOC_SYSTEM_AGP, ksmedia/KS_CAPTURE_ALLOC_VRAM, ksmedia/KS_CAPTURE_ALLOC_VRAM_MAPPED, ksmedia/PCAPTURE_MEMORY_ALLOCATION_FLAGS, stream.capture_memory_allocation_flags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	CAPTURE_MEMORY_ALLOCATION_FLAGS
product:
- Windows
targetos: Windows
req.typenames: CAPTURE_MEMORY_ALLOCATION_FLAGS, *PCAPTURE_MEMORY_ALLOCATION_FLAGS
---

# CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration


## -description


The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff565209">KSPROPERTY_PREFERRED_CAPTURE_SURFACE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565130">KSPROPERTY_CURRENT_CAPTURE_SURFACE</a> requests use this type to specify property values.


## -enum-fields




### -field KS_CAPTURE_ALLOC_INVALID

Invalid memory surface.


### -field KS_CAPTURE_ALLOC_SYSTEM

Not currently supported. 


### -field KS_CAPTURE_ALLOC_VRAM

Identifies a surface in display memory.


### -field KS_CAPTURE_ALLOC_SYSTEM_AGP

Identifies a surface in system memory that is tagged as AGP accessible. 


### -field KS_CAPTURE_ALLOC_VRAM_MAPPED

Not currently supported.  


### -field KS_CAPTURE_ALLOC_SECURE_BUFFER




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565130">KSPROPERTY_CURRENT_CAPTURE_SURFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565209">KSPROPERTY_PREFERRED_CAPTURE_SURFACE</a>
 

 

