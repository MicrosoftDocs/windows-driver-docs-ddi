---
UID: NS:d3d10umddi.D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
title: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW (d3d10umddi.h)
description: The D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure describes a one-dimensional texture (1-D) that is used to create an unordered access view in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_tex1d_unorderedaccessview.htm
ms.assetid: aeee9194-2824-43ff-8225-4c0ef666e44f
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure"]
ms.keywords: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW, D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_46a7f507-bfcb-4d1d-a905-ea60655785d6.xml, d3d10umddi/D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW, display.d3d11ddiarg_tex1d_unorderedaccessview
f1_keywords:
 - "d3d10umddi/D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW"
 - "D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
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
- D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW
---

# D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure


## -description


The D3D11DDIARG_TEX1D_UNORDEREDACCESSVIEW structure describes a one-dimensional texture (1-D) that is used to create an unordered access view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a> function. 


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize">CalcPrivateUnorderedAccessViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>
 

 

