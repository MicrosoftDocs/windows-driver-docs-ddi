---
UID: NS:d3d10umddi.D3D10DDIARG_CREATERESOURCE
title: D3D10DDIARG_CREATERESOURCE (d3d10umddi.h)
description: Describes a resource to create.
old-location: display\d3d10ddiarg_createresource.htm
ms.assetid: 2d67a00e-a3ba-4a19-ac6b-0b12d079435c
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_CREATERESOURCE, D3D10DDIARG_CREATERESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3f91ee50-2bdd-4206-afe6-d8b79d3b7d80.xml, d3d10umddi/D3D10DDIARG_CREATERESOURCE, display.d3d10ddiarg_createresource
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_CREATERESOURCE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_CREATERESOURCE
---

# D3D10DDIARG_CREATERESOURCE structure


## -description


Describes a resource to create.


## -struct-fields




### -field pMipInfoList

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541845">D3D10DDI_MIPINFO</a> structures that contains dimensions for MIP levels. For resource formats where a single pixel or texel cannot be referenced directly with a byte address, the dimensions of the physical resource are typically larger or equal to the texel dimensions, in order to satisfy the necessary space requirements. For example, to create a fully mipped BC1 Texture2D, where the most detailed level is 8x8, the <b>pMipInfoList</b> array is:  { { 8, 8, 1, 8, 8, 1 }, { 4, 4, 1, 4, 4, 1 }, { 2, 2, 1, 4, 4, 1 }, { 1, 1, 1, 4, 4, 1 } }.


### -field pInitialDataUP

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541909">D3D10_DDIARG_SUBRESOURCE_UP</a> structures that provides initialization information for the resource's list of subresources.


### -field ResourceDimension

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a> that indicates the resource type and dimensionality.


### -field Usage

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff542008">D3D10_DDI_RESOURCE_USAGE</a> that indicates how the resource is used.


### -field BindFlags

[in] A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541995">D3D10_DDI_RESOURCE_BIND_FLAG</a> values that indicates how the resource is bound.


### -field MapFlags

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541957">D3D10_DDI_MAP</a> that indicates the access level to map to the resource.


### -field MiscFlags

[in] A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542004">D3D10_DDI_RESOURCE_MISC_FLAG</a> values that indicates miscellaneous information about the resource.


### -field Format

[in] A value of type <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> that indicates the pixel format of the resource.


### -field SampleDesc

[in] A value of type <a href="https://msdn.microsoft.com/a8071d3c-dc78-43fe-84f6-421418e16b02">DXGI_SAMPLE_DESC</a> that describes the sample count and quality of the resource.


### -field MipLevels

[in] The number of MIP-map levels for the resource.


### -field ArraySize

[in] The number of array elements for a 2-D texture or 1-D texture. <b>ArraySize</b> must be set to 6 for a cube texture.

Beginning in Windows 8, if the driver must create a stereo back buffer, it should set this member to a value of 2.


### -field pPrimaryDesc

[in, out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557511">DXGI_DDI_PRIMARY_DESC</a> structure that describes a resource that is used as a primary.

The Microsoft Direct3D runtime sets <b>pPrimaryDesc</b> to a non-<b>NULL</b> value only if the D3D10_DDI_BIND_PRESENT bit is set in the <b>BindFlags</b> member; however, even if D3D10_DDI_BIND_PRESENT is set, the runtime does not always set <b>pPrimaryDesc</b> to non-<b>NULL</b>. Setting <b>pPrimaryDesc</b> to non-<b>NULL</b> indicates that the runtime will use the created resource as a primary (that is, the resource is scanned out to the display) and in flip-style present operations. 

The user-mode display driver can return the DXGI_DDI_PRIMARY_DRIVER_FLAG_NO_SCANOUT flag in the <b>DriverFlags</b> member of DXGI_DDI_PRIMARY_DESC to prevent the runtime from performing flip-style present operations. 

If <b>pPrimaryDesc</b> is set to <b>NULL</b>, the runtime will use the created resource in copy-style (bit-block transfer) present operations. 


## -see-also




<a href="https://msdn.microsoft.com/c21839f0-8302-49f9-a2b4-4009fbd2d88c">CreateResource(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541845">D3D10DDI_MIPINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541909">D3D10_DDIARG_SUBRESOURCE_UP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541957">D3D10_DDI_MAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541995">D3D10_DDI_RESOURCE_BIND_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542004">D3D10_DDI_RESOURCE_MISC_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542008">D3D10_DDI_RESOURCE_USAGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557511">DXGI_DDI_PRIMARY_DESC</a>



<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>



<a href="https://msdn.microsoft.com/a8071d3c-dc78-43fe-84f6-421418e16b02">DXGI_SAMPLE_DESC</a>
 

 

