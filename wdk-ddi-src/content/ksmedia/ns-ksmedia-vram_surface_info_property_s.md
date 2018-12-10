---
UID: NS:ksmedia.__unnamed_struct_82
title: VRAM_SURFACE_INFO_PROPERTY_S
author: windows-driver-content
description: The VRAM_SURFACE_INFO_PROPERTY_S structure describes property items in the KSPROPSETID_VramCapture property set.
old-location: stream\vram_surface_info_property_s.htm
tech.root: stream
ms.assetid: 9bb24ca3-2684-4873-8136-c560f3374310
ms.date: 04/23/2018
ms.keywords: "*PVRAM_SURFACE_INFO_PROPERTY_S, PVRAM_SURFACE_INFO_PROPERTY_S, PVRAM_SURFACE_INFO_PROPERTY_S structure pointer [Streaming Media Devices], VRAM_SURFACE_INFO_PROPERTY_S, VRAM_SURFACE_INFO_PROPERTY_S structure [Streaming Media Devices], avstruct_f0149912-f7c6-4cf5-bc5e-107c03c7823f.xml, ksmedia/PVRAM_SURFACE_INFO_PROPERTY_S, ksmedia/VRAM_SURFACE_INFO_PROPERTY_S, stream.vram_surface_info_property_s"
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
-	VRAM_SURFACE_INFO_PROPERTY_S
product:
- Windows
targetos: Windows
req.typenames: VRAM_SURFACE_INFO_PROPERTY_S, *PVRAM_SURFACE_INFO_PROPERTY_S
---

# VRAM_SURFACE_INFO_PROPERTY_S structure


## -description


The VRAM_SURFACE_INFO_PROPERTY_S structure describes property items in the KSPROPSETID_VramCapture property set.


## -struct-fields




### -field Property

This member specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field pVramSurfaceInfo

This member specifies a pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff568783">VRAM_SURFACE_INFO</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568783">VRAM_SURFACE_INFO</a>
 

 

