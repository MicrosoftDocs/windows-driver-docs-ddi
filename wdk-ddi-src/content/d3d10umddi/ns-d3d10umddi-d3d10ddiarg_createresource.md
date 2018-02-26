---
UID: NS:d3d10umddi.D3D10DDIARG_CREATERESOURCE
title: D3D10DDIARG_CREATERESOURCE
author: windows-driver-content
description: Describes a resource to create.
old-location: display\d3d10ddiarg_createresource.htm
old-project: display
ms.assetid: 2d67a00e-a3ba-4a19-ac6b-0b12d079435c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 0, 1, 3, A, C, D, D3D10DDIARG_CREATERESOURCE, D3D10DDIARG_CREATERESOURCE structure [Display Devices], E, G, I, O, R, S, T, U, UMDisplayDriver_Dx10param_Structs_3f91ee50-2bdd-4206-afe6-d8b79d3b7d80.xml, _, d3d10umddi/D3D10DDIARG_CREATERESOURCE, display.d3d10ddiarg_createresource"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10DDIARG_CREATERESOURCE
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATERESOURCE
---

# D3D10DDIARG_CREATERESOURCE structure


## -description


Describes a resource to create.


## -syntax


````
typedef struct D3D10DDIARG_CREATERESOURCE {
  const D3D10DDI_MIPINFO            *pMipInfoList;
  const D3D10_DDIARG_SUBRESOURCE_UP *pInitialDataUP;
  D3D10DDIRESOURCE_TYPE             ResourceDimension;
  UINT                              Usage;
  UINT                              BindFlags;
  UINT                              MapFlags;
  UINT                              MiscFlags;
  DXGI_FORMAT                       Format;
  DXGI_SAMPLE_DESC                  SampleDesc;
  UINT                              MipLevels;
  UINT                              ArraySize;
  DXGI_DDI_PRIMARY_DESC             *pPrimaryDesc;
} D3D10DDIARG_CREATERESOURCE;
````


## -struct-fields




### -field pMipInfoList

[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_mipinfo.md">D3D10DDI_MIPINFO</a> structures that contains dimensions for MIP levels. For resource formats where a single pixel or texel cannot be referenced directly with a byte address, the dimensions of the physical resource are typically larger or equal to the texel dimensions, in order to satisfy the necessary space requirements. For example, to create a fully mipped BC1 Texture2D, where the most detailed level is 8x8, the <b>pMipInfoList</b> array is:  { { 8, 8, 1, 8, 8, 1 }, { 4, 4, 1, 4, 4, 1 }, { 2, 2, 1, 4, 4, 1 }, { 1, 1, 1, 4, 4, 1 } }.


### -field pInitialDataUP

[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddiarg_subresource_up.md">D3D10_DDIARG_SUBRESOURCE_UP</a> structures that provides initialization information for the resource's list of subresources.


### -field ResourceDimension

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a> that indicates the resource type and dimensionality.


### -field Usage

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_usage.md">D3D10_DDI_RESOURCE_USAGE</a> that indicates how the resource is used.


### -field BindFlags

[in] A valid bitwise OR of <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a> values that indicates how the resource is bound.


### -field MapFlags

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a> that indicates the access level to map to the resource.


### -field MiscFlags

[in] A valid bitwise OR of <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md">D3D10_DDI_RESOURCE_MISC_FLAG</a> values that indicates miscellaneous information about the resource.


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

[in, out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_primary_desc.md">DXGI_DDI_PRIMARY_DESC</a> structure that describes a resource that is used as a primary.

The Microsoft Direct3D runtime sets <b>pPrimaryDesc</b> to a non-<b>NULL</b> value only if the D3D10_DDI_BIND_PRESENT bit is set in the <b>BindFlags</b> member; however, even if D3D10_DDI_BIND_PRESENT is set, the runtime does not always set <b>pPrimaryDesc</b> to non-<b>NULL</b>. Setting <b>pPrimaryDesc</b> to non-<b>NULL</b> indicates that the runtime will use the created resource as a primary (that is, the resource is scanned out to the display) and in flip-style present operations. 

The user-mode display driver can return the DXGI_DDI_PRIMARY_DRIVER_FLAG_NO_SCANOUT flag in the <b>DriverFlags</b> member of DXGI_DDI_PRIMARY_DESC to prevent the runtime from performing flip-style present operations. 

If <b>pPrimaryDesc</b> is set to <b>NULL</b>, the runtime will use the created resource in copy-style (bit-block transfer) present operations. 


## -see-also

<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_usage.md">D3D10_DDI_RESOURCE_USAGE</a>



<a href="https://msdn.microsoft.com/a8071d3c-dc78-43fe-84f6-421418e16b02">DXGI_SAMPLE_DESC</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md">D3D10_DDI_RESOURCE_MISC_FLAG</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_mipinfo.md">D3D10DDI_MIPINFO</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddiarg_subresource_up.md">D3D10_DDIARG_SUBRESOURCE_UP</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_primary_desc.md">DXGI_DDI_PRIMARY_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_CREATERESOURCE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

