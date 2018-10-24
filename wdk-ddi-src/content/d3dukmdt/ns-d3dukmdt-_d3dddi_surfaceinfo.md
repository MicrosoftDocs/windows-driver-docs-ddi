---
UID: NS:d3dukmdt._D3DDDI_SURFACEINFO
title: "_D3DDDI_SURFACEINFO"
author: windows-driver-content
description: The D3DDDI_SURFACEINFO structure describes a resource type, such as a surface.
old-location: display\d3dddi_surfaceinfo.htm
tech.root: display
ms.assetid: 347edff7-b209-4b60-aabc-5ee7963c8164
ms.date: 05/10/2018
ms.keywords: D3DDDI_SURFACEINFO, D3DDDI_SURFACEINFO structure [Display Devices], D3D_other_Structs_03e742b5-062c-46d3-bedf-25aee3582dfc.xml, _D3DDDI_SURFACEINFO, d3dukmdt/D3DDDI_SURFACEINFO, display.d3dddi_surfaceinfo
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_SURFACEINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_SURFACEINFO
---

# _D3DDDI_SURFACEINFO structure


## -description


The D3DDDI_SURFACEINFO structure describes a resource type, such as a surface.


## -struct-fields




### -field Width

[in] The width, in pixels, of the surface or volume or the length, in pixels, of the linear resource.


### -field Height

[in] The height, in pixels, of the surface or volume.


### -field Depth

[in] The depth, in pixels, of the volume.


### -field pSysMem

[in] A pointer to a buffer that contains the contents of the resource if the resource exists in system memory and <b>NULL</b> if the resource exists in video memory.

Note that this member is valid only if the <b>Pool</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure for creating the resource is set to the D3DDDIPOOL_SYSTEMMEM value.


### -field SysMemPitch

[in] The pitch, in bytes, of the surface--that is, the distance, in bytes, to the start of the next line.


### -field SysMemSlicePitch

[in] The slice, in bytes, of the volume.


## -see-also




<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a>
 

 

