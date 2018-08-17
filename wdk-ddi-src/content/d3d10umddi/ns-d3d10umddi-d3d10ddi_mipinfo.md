---
UID: NS:d3d10umddi.D3D10DDI_MIPINFO
title: D3D10DDI_MIPINFO
author: windows-driver-content
description: The D3D10DDI_MIPINFO structure describes the MIP-level texture and physical coordinates of a surface.
old-location: display\d3d10ddi_mipinfo.htm
ms.assetid: 5f00ff32-5ecf-40ca-91bb-aacc542bb7f4
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D10DDI_MIPINFO, D3D10DDI_MIPINFO structure [Display Devices], UMDisplayDriver_Dx10param_Structs_67768e5f-a18d-4bd9-a1be-96587f267c36.xml, d3d10umddi/D3D10DDI_MIPINFO, display.d3d10ddi_mipinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3d10umddi.h
api_name:
-	D3D10DDI_MIPINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_MIPINFO
---

# D3D10DDI_MIPINFO structure


## -description


The D3D10DDI_MIPINFO structure describes the MIP-level texture and physical coordinates of a surface.


## -struct-fields




### -field TexelWidth

[in] The width, in texels, of the surface or volume, or the length, in texels, of the linear resource.


### -field TexelHeight

[in] The height, in texels, of the surface or volume.


### -field TexelDepth

[in] The depth, in texels, of the volume.


### -field PhysicalWidth

[in] The width, in pixels, of the surface or volume, or the length, in pixels, of the linear resource.


### -field PhysicalHeight

[in] The height, in pixels, of the surface or volume.


### -field PhysicalDepth

[in] The depth, in pixels, of the volume.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>
 

 

