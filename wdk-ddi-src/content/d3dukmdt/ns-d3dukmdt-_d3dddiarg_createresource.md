---
UID: NS:d3dukmdt._D3DDDIARG_CREATERESOURCE
title: "_D3DDDIARG_CREATERESOURCE"
author: windows-driver-content
description: The D3DDDIARG_CREATERESOURCE structure contains information for creating a resource.
old-location: display\d3dddiarg_createresource.htm
old-project: display
ms.assetid: 022047a4-105e-4859-ba37-fb408f903e7b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_CREATERESOURCE, D3DDDIARG_CREATERESOURCE structure [Display Devices], UMDisplayDriver_param_Structs_c8d46034-b0b8-4909-962d-683be7aa099d.xml, _D3DDDIARG_CREATERESOURCE, d3dukmdt/D3DDDIARG_CREATERESOURCE, display.d3dddiarg_createresource
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DDDIARG_CREATERESOURCE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATERESOURCE
---

# _D3DDDIARG_CREATERESOURCE structure


## -description


The D3DDDIARG_CREATERESOURCE structure contains information for creating a resource.


## -struct-fields




### -field Format

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>-typed value that indicates the format of the resources.


### -field Pool

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544634">D3DDDI_POOL</a>-typed value that indicates the type of memory pool that the resources are created from.


### -field MultisampleType

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544324">D3DDDIMULTISAMPLE_TYPE</a>-typed value that indicates the number of samples for a multiple-sampled surface. If the surface is not multiple sampled, this value is D3DDDIMULTISAMPLE_NONE (0).


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

[in/out] A handle to the resource. On input to the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function, <b>hResource</b> specifies the handle that the driver should use anytime it calls back into the Microsoft Direct3D runtime. 

The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function, <b>hResource</b> specifies the handle that the Direct3D runtime should use in subsequent driver calls to identify the resource.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544644">D3DDDI_RESOURCEFLAGS</a> structure that identifies the type of resources to create. Note that some of the bit-field flags in <b>D3DDDI_RESOURCEFLAGS</b> require that additional bit-field flags are set as well.


### -field Rotation

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the resource. 

For example, consider that the user-mode display driver receives a request for a 480x640 surface to be rotated 90 degrees (<b>D3DDDI_ROTATION_90</b>). The driver should allocate the surface in 640x480 mode for scanning purposes. When rendering to the surface, the driver should perform the 90 degree rotation. 

Orientations other than <b>D3DDDI_ROTATION_IDENTITY</b> are set only when the <b>Primary</b> bit-field flag is also set in the <b>Flags</b> member.


## -see-also




<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544324">D3DDDIMULTISAMPLE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544634">D3DDDI_POOL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544641">D3DDDI_RATIONAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a>
 

 

