---
UID: NS:ksmedia.VRAM_SURFACE_INFO
title: VRAM_SURFACE_INFO
author: windows-driver-content
description: The VRAM_SURFACE_INFO structure describes a region of system or display memory into which an AVStream minidriver captures audio or video data.
old-location: stream\vram_surface_info.htm
tech.root: stream
ms.assetid: 6fce78f7-a23e-4651-b6d8-b3d5387ccc27
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PVRAM_SURFACE_INFO, PVRAM_SURFACE_INFO, PVRAM_SURFACE_INFO structure pointer [Streaming Media Devices], VRAM_SURFACE_INFO, VRAM_SURFACE_INFO structure [Streaming Media Devices], avstruct_ac2ca5de-0eea-453b-b3fd-79874fd2242a.xml, ksmedia/PVRAM_SURFACE_INFO, ksmedia/VRAM_SURFACE_INFO, stream.vram_surface_info"
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
-	VRAM_SURFACE_INFO
product:
- Windows
targetos: Windows
req.typenames: VRAM_SURFACE_INFO, *PVRAM_SURFACE_INFO
---

# VRAM_SURFACE_INFO structure


## -description


The VRAM_SURFACE_INFO structure describes a region of system or display memory into which an AVStream minidriver captures audio or video data.


## -struct-fields




### -field hSurface

A pointer to a kernel-mode handle that identifies the VRAM surface.


### -field VramPhysicalAddress

This member contains the physical address of the surface in display memory. The minidriver fills in this member in the handler for <a href="https://msdn.microsoft.com/library/windows/hardware/ff565177">KSPROPERTY_MAP_CAPTURE_HANDLE_TO_VRAM_ADDRESS</a>.


### -field cbCaptured

This member specifies the number of bytes copied into the VRAM surface. The minidriver sets this value.


### -field dwWidth

This member specifies the width of the video data in pixels. The minidriver sets this value.


### -field dwHeight

This member specifies the height of the video data, in pixels. The minidriver sets this value.


### -field dwLinearSize

This member specifies the linear size, in bytes, of a nonrectangular surface. The minidriver sets this value.


### -field lPitch

This member specifies the pitch of the surface; that is, the distance, in bytes, to the start of the next line. This is also known as the <i>stride</i> of the surface. The minidriver sets this value.


### -field ullReserved

The minidriver can use this member to store information about the surface as it handles a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565177">KSPROPERTY_MAP_CAPTURE_HANDLE_TO_VRAM_ADDRESS</a> request. Use caution, however; this structure does not persist across <a href="https://msdn.microsoft.com/library/windows/hardware/ff556351">AVStrMiniPinProcess</a> calls.


## -remarks



When the minidriver receives VRAM_SURFACE_INFO through a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565177">KSPROPERTY_MAP_CAPTURE_HANDLE_TO_VRAM_ADDRESS</a> property call, the members following <b>VramPhysicalAddress</b> in the member list (except for <b>ullReserved</b>) are zeroed out. The capture driver can store capture-related private data in these members.

AVStream then stores this information in the stream header and returns it to the minidriver in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556351">AVStrMiniPinProcess</a> callback function.

The data in these members persists for the lifetime of the stream header. When all clones are deleted or the leading edge is advanced, this data is no longer accessible.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556351">AVStrMiniPinProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565177">KSPROPERTY_MAP_CAPTURE_HANDLE_TO_VRAM_ADDRESS</a>
 

 

