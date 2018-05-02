---
UID: NS:d3dukmdt._D3DDDIARG_CREATERESOURCE2
title: "_D3DDDIARG_CREATERESOURCE2"
author: windows-driver-content
description: Contains information for creating a resource. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3dddiarg_createresource2.htm
old-project: display
ms.assetid: 337874d1-9f9b-429d-a970-60b5d86ac7a2
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_CREATERESOURCE2, D3DDDIARG_CREATERESOURCE2 structure [Display Devices], _D3DDDIARG_CREATERESOURCE2, d3dukmdt/D3DDDIARG_CREATERESOURCE2, display.d3dddiarg_createresource2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dukmdt.h
api_name:
-	D3DDDIARG_CREATERESOURCE2
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATERESOURCE2
---

# _D3DDDIARG_CREATERESOURCE2 structure


## -description


Contains information for creating a resource. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -struct-fields




### -field Format

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> that indicates the format of the resources.


### -field Pool

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544634">D3DDDI_POOL</a> that indicates the type of memory pool that the resources are created from.


### -field MultisampleType

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544324">D3DDDIMULTISAMPLE_TYPE</a> that indicates the number of samples for a multiple-sampled surface. If the surface is not multiple sampled, this value is D3DDDIMULTISAMPLE_NONE (0).


### -field MultisampleQuality

[in] The quality level of rendering samples in a multiple-sampled surface. The quality level must be a number from 0 through 7 that represents a quality level from 1 through 8, respectively.

Note that even if the surface is not multiple-sampled (that is, if <b>D3DDDIMULTISAMPLE_NONE</b> is specified in <b>MultisampleType</b>) it can still have a quality level that is greater than 1 (which is specified by using a number greater than 0).


### -field pSurfList

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a> structures for the list of surfaces (or other resource types) to create.


### -field SurfCount

[in] The number of resources in the array that is specified by the <b>pSurfList</b> member.


### -field MipLevels

[in] The number of MIP-map levels for the resources.


### -field Fvf

[in] The FVF format for vertex buffers.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the primary surface is created on (if the resource contains a primary surface).


### -field RefreshRate

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544641">D3DDDI_RATIONAL</a> structure that specifies the refresh rate that the resource is used with. This member is applicable only if the resource is the primary surface and the <b>MatchGdiPrimary</b> bit-field flag is not set in the <b>Flags</b> member. In addition, if the <b>InterlacedRefresh</b> bit-field flag is set in <b>Flags</b>, the user-mode display driver determines that the refresh rate is interleaved (otherwise, progressive).


### -field hResource

[in/out] A handle to the resource. On input to the <a href="https://msdn.microsoft.com/a8326707-cffc-4a20-ad3d-c7862661f513">CreateResource2</a> function, <b>hResource</b> specifies the handle that the driver should use anytime it calls back into the Microsoft Direct3D runtime. 

The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="https://msdn.microsoft.com/a8326707-cffc-4a20-ad3d-c7862661f513">CreateResource2</a> function, <b>hResource</b> specifies the handle that the Direct3D runtime should use in subsequent driver calls to identify the resource.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a> structure that identifies the type of resources to create. Note that some of the bit-field flags in <b>D3DDDI_RESOURCEFLAGS</b> require that additional bit-field flags are set as well.


### -field Rotation

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the resource. 

For example, consider that the user-mode display driver receives a request for a 480x640 surface to be rotated 90 degrees (<b>D3DDDI_ROTATION_90</b>). The driver should allocate the surface in 640x480 mode for scanning purposes. When rendering to the surface, the driver should perform the 90 degree rotation. 

Orientations other than <b>D3DDDI_ROTATION_IDENTITY</b> are set only when the <b>Primary</b> bit-field flag is also set in the <b>Flags</b> member.


### -field Flags2

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/hh439286">D3DDDI_RESOURCEFLAGS2</a> structure that identifies the type of resources to create. Note that some of the bit-field flags in <b>D3DDDI_RESOURCEFLAGS2</b> require that additional bit-field flags are set as well.


## -see-also




<a href="https://msdn.microsoft.com/a8326707-cffc-4a20-ad3d-c7862661f513">CreateResource2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544324">D3DDDIMULTISAMPLE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544634">D3DDDI_POOL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544641">D3DDDI_RATIONAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439286">D3DDDI_RESOURCEFLAGS2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a>
 

 

