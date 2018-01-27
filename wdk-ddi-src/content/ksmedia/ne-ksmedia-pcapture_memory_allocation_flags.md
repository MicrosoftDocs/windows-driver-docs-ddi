---
UID: NE:ksmedia.PCAPTURE_MEMORY_ALLOCATION_FLAGS
title: *PCAPTURE_MEMORY_ALLOCATION_FLAGS
author: windows-driver-content
description: The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data.
old-location: stream\capture_memory_allocation_flags.htm
old-project: stream
ms.assetid: 3b96301a-28a5-494b-bd12-8d3d4516730e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_CAPTURE_ALLOC_INVALID, stream.capture_memory_allocation_flags, ksmedia/KS_CAPTURE_ALLOC_SYSTEM_AGP, KS_CAPTURE_ALLOC_SYSTEM_AGP, KS_CAPTURE_ALLOC_VRAM_MAPPED, ksmedia/KS_CAPTURE_ALLOC_SYSTEM, *PCAPTURE_MEMORY_ALLOCATION_FLAGS, CAPTURE_MEMORY_ALLOCATION_FLAGS, ksmedia/CAPTURE_MEMORY_ALLOCATION_FLAGS, PCAPTURE_MEMORY_ALLOCATION_FLAGS, KS_CAPTURE_ALLOC_SYSTEM, ksmedia/KS_CAPTURE_ALLOC_VRAM, KS_CAPTURE_ALLOC_VRAM, ksmedia/KS_CAPTURE_ALLOC_VRAM_MAPPED, PCAPTURE_MEMORY_ALLOCATION_FLAGS enumeration pointer [Streaming Media Devices], CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration [Streaming Media Devices], ksmedia/PCAPTURE_MEMORY_ALLOCATION_FLAGS, avstruct_2c1411b2-f4a6-44f9-ba68-63f2f5654105.xml, ksmedia/KS_CAPTURE_ALLOC_INVALID
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ksmedia.h
apiname: 
-	CAPTURE_MEMORY_ALLOCATION_FLAGS
product: Windows
targetos: Windows
req.typenames: CAPTURE_MEMORY_ALLOCATION_FLAGS, *PCAPTURE_MEMORY_ALLOCATION_FLAGS
---

# *PCAPTURE_MEMORY_ALLOCATION_FLAGS enumeration


## -description


The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff565209">KSPROPERTY_PREFERRED_CAPTURE_SURFACE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565130">KSPROPERTY_CURRENT_CAPTURE_SURFACE</a> requests use this type to specify property values.


## -syntax


````
typedef enum  { 
  KS_CAPTURE_ALLOC_INVALID      = 0,
  KS_CAPTURE_ALLOC_SYSTEM       = 0x0001,
  KS_CAPTURE_ALLOC_VRAM         = 0x0002,
  KS_CAPTURE_ALLOC_SYSTEM_AGP   = 0x0004,
  KS_CAPTURE_ALLOC_VRAM_MAPPED  = 0x0008
} CAPTURE_MEMORY_ALLOCATION_FLAGS, *PCAPTURE_MEMORY_ALLOCATION_FLAGS;
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

