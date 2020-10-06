---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
title: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW (d3d10umddi.h)
description: The D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure describes the unordered access view to create.
old-location: display\d3d11ddiarg_createunorderedaccessview.htm
ms.assetid: 3c977fe6-d0f9-4edc-abeb-0725d68a482d
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure"]
ms.keywords: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW, D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_e6b10da8-f790-4182-926a-a7f183dcd59b.xml, d3d10umddi/D3D11DDIARG_CREATEUNORDEREDACCESSVIEW, display.d3d11ddiarg_createunorderedaccessview
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
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
f1_keywords:
 - D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
 - d3d10umddi/D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_CREATEUNORDEREDACCESSVIEW
---

# D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure


## -description

The D3D11DDIARG_CREATEUNORDEREDACCESSVIEW structure describes the unordered access view to create.

## -struct-fields

### -field hDrvResource

[in] A handle to the unordered access block.

### -field Format

[in] A DXGI_FORMAT-typed value that indicates the pixel format of the unordered access block.

### -field ResourceDimension

[in] A <a href="/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>-typed value that indicates the resource type and dimensionality of the unordered access block. The Direct3D runtime will never set <b>ResourceDimension</b> to D3D10DDIRESOURCE_TEXTURECUBE.

### -field Buffer

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_BUFFER, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a> structure for a buffer.

### -field Tex1D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE1D, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tex1d_unorderedaccessview">D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW</a> structure for a one-dimensional texture.

### -field Tex2D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE2D, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tex2d_unorderedaccessview">D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW</a> structure for a two-dimensional texture.

### -field Tex3D

[in] If the value in the <b>ResourceDimension</b> member is set to D3D10DDIRESOURCE_TEXTURE3D, a member in the union that is contained in D3D11DDIARG_CREATEUNORDEREDACCESSVIEW that can hold a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tex3d_unorderedaccessview">D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW</a> structure for a three-dimensional texture.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize">CalcPrivateUnorderedAccessViewSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a>



<a href="/previous-versions/windows/hardware/drivers/ff541810(v=vs.85)">D3D10DDIRESOURCE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tex1d_unorderedaccessview">D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tex2d_unorderedaccessview">D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_tex3d_unorderedaccessview">D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW</a>