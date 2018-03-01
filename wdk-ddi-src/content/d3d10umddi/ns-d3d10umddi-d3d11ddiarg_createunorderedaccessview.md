---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
title: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure describes the unordered access view to create.
old-location: display\d3d11ddiarg_createunorderedaccessview.htm
old-project: display
ms.assetid: 3c977fe6-d0f9-4edc-abeb-0725d68a482d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW, D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e6b10da8-f790-4182-926a-a7f183dcd59b.xml, d3d10umddi/D3D11DDIARG_CREATEUNORDEREDACCESSVIEW, display.d3d11ddiarg_createunorderedaccessview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
---

# D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure


## -description


The D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure describes the unordered access view to create.


## -syntax


````
typedef struct D3D11DDIARG_CREATEUNORDEREDACCESSVIEW {
  D3D10DDI_HRESOURCE    hDrvResource;
  DXGI_FORMAT           Format;
  D3D10DDIRESOURCE_TYPE ResourceDimension;
  union {
    D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW Buffer;
    D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW  Tex1D;
    D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW  Tex2D;
    D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW  Tex3D;
  };
} D3D11DDIARG_CREATEUNORDEREDACCESSVIEW;
````


## -struct-fields




### -field hDrvResource

[in] A handle to the unordered access block. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the unordered access block.


### -field ResourceDimension

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the unordered access block. The Direct3D runtime will never set <b>ResourceDimension</b> to D3D10DDIRESOURCE_TEXTURECUBE. 


#### - Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a> structure for a buffer. 


#### - Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tex1d_unorderedaccessview.md">D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW</a> structure for a one-dimensional texture. 


#### - Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tex2d_unorderedaccessview.md">D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW</a> structure for a two-dimensional texture. 


#### - Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tex3d_unorderedaccessview.md">D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW</a> structure for a three-dimensional texture. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541810">D3D10DDIRESOURCE_TYPE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tex3d_unorderedaccessview.md">D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tex1d_unorderedaccessview.md">D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tex2d_unorderedaccessview.md">D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview.md">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

