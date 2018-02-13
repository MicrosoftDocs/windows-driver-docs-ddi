---
UID: NS:d3d10umddi.D3D11DDIARG_CREATERESOURCE
title: D3D11DDIARG_CREATERESOURCE
author: windows-driver-content
description: Describes a resource to create.
old-location: display\d3d11ddiarg_createresource.htm
old-project: display
ms.assetid: 4cdc5d74-ef53-47aa-91ed-0b71dfe688dc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11DDIARG_CREATERESOURCE structure [Display Devices], display.d3d11ddiarg_createresource, D3D11DDIARG_CREATERESOURCE, UMDisplayDriver_Dx11param_Structs_86915c01-2d64-42d6-bae0-2a83ba1dda80.xml, d3d10umddi/D3D11DDIARG_CREATERESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CREATERESOURCE is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_CREATERESOURCE
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATERESOURCE
---

# D3D11DDIARG_CREATERESOURCE structure


## -description


Describes a resource to create.


## -syntax


````
typedef struct D3D11DDIARG_CREATERESOURCE {
  const D3D10DDI_MIPINFO               *pMipInfoList;
  const D3D10_DDIARG_SUBRESOURCE_UP    *pInitialDataUP;
  D3D10DDIRESOURCE_TYPE                ResourceDimension;
  UINT                                 Usage;
  UINT                                 BindFlags;
  UINT                                 MapFlags;
  UINT                                 MiscFlags;
  DXGI_FORMAT                          Format;
  DXGI_SAMPLE_DESC                     SampleDesc;
  UINT                                 MipLevels;
  UINT                                 ArraySize;
  DXGI_DDI_PRIMARY_DESC                *pPrimaryDesc;
  UINT                                 ByteStride;
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE DecoderBufferType;
#endif 
} D3D11DDIARG_CREATERESOURCE;
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

[in] A valid bitwise OR of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a> that indicates how the resource is bound.


### -field MapFlags

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a> that indicates the access level to map to the resource.


### -field MiscFlags

[in] A valid bitwise OR of values of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md">D3D10_DDI_RESOURCE_MISC_FLAG</a> that indicates miscellaneous information about the resource.


### -field Format

[in] A value of type <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> that indicates the pixel format of the resource.


### -field SampleDesc

[in] A value of type <a href="https://msdn.microsoft.com/a8071d3c-dc78-43fe-84f6-421418e16b02">DXGI_SAMPLE_DESC</a> that describes the sample count and quality of the resource.


### -field MipLevels

[in] The number of MIP-map levels for the resource.


### -field ArraySize

[in] The number of array elements for a 2-D texture or 1-D texture. <b>ArraySize</b> must be set to 6 for a cube texture.

Beginning in Windows 8, if the driver must create a stereo back buffer, it should set the <b>ArraySize</b> member of the <b>D3D11DDIARG_CREATERESOURCE</b> structure to a value of 2.


### -field pPrimaryDesc

[in, out] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_primary_desc.md">DXGI_DDI_PRIMARY_DESC</a> structure that describes a resource that is used as a primary.

The Microsoft Direct3D runtime sets <b>pPrimaryDesc</b> to a non-<b>NULL</b> value only if the D3D10_DDI_BIND_PRESENT bit is set in the <b>BindFlags</b> member; however, even if D3D10_DDI_BIND_PRESENT is set, the runtime does not always set <b>pPrimaryDesc</b> to non-<b>NULL</b>. Setting <b>pPrimaryDesc</b> to non-<b>NULL</b> indicates that the runtime will use the created resource as a primary (that is, the resource is scanned out to the display) and in flip-style present operations. 

The user-mode display driver can return the DXGI_DDI_PRIMARY_DRIVER_FLAG_NO_SCANOUT flag in the <b>DriverFlags</b> member of DXGI_DDI_PRIMARY_DESC to prevent the runtime from performing flip-style present operations. 

If <b>pPrimaryDesc</b> is set to <b>NULL</b>, the runtime will use the created resource in; copy-style (bit-block transfer) present operations. 


### -field ByteStride

[in] The size, in bytes, from one scan line to the next scan line in the surface. 


### -field DecoderBufferType

[in] A value of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> that indicates the  buffer type used by the video decoder.

If the driver does not check that D3D11DDI_MINOR_HEADER_VERSION &gt;= 3 before accessing this  structure member, it should access this member only when the D3D11_DDI_BIND_DECODER flag is set in the <b>BindFlags</b> member.


### -field TextureLayout

 




## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_primary_desc.md">DXGI_DDI_PRIMARY_DESC</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_usage.md">D3D10_DDI_RESOURCE_USAGE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>



<a href="https://msdn.microsoft.com/a8071d3c-dc78-43fe-84f6-421418e16b02">DXGI_SAMPLE_DESC</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddiarg_subresource_up.md">D3D10_DDIARG_SUBRESOURCE_UP</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md">D3D10_DDI_RESOURCE_MISC_FLAG</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_mipinfo.md">D3D10DDI_MIPINFO</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_CREATERESOURCE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

