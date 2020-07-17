---
UID: NS:d3d10umddi.D3D10DDI_MAPPED_SUBRESOURCE
title: D3D10DDI_MAPPED_SUBRESOURCE (d3d10umddi.h)
description: The D3D10DDI_MAPPED_SUBRESOURCE structure describes a subresource that the driver maps to through a call to the driver's ResourceMap function.
old-location: display\d3d10ddi_mapped_subresource.htm
ms.assetid: a55f9aee-c6a5-4391-aad1-4003e58692cd
ms.date: 05/10/2018
keywords: ["D3D10DDI_MAPPED_SUBRESOURCE structure"]
ms.keywords: D3D10DDI_MAPPED_SUBRESOURCE, D3D10DDI_MAPPED_SUBRESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_19502bf4-94a6-48d5-8294-c058c254540f.xml, d3d10umddi/D3D10DDI_MAPPED_SUBRESOURCE, display.d3d10ddi_mapped_subresource
f1_keywords:
 - "d3d10umddi/D3D10DDI_MAPPED_SUBRESOURCE"
 - "D3D10DDI_MAPPED_SUBRESOURCE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows Vista.
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
- D3D10DDI_MAPPED_SUBRESOURCE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_MAPPED_SUBRESOURCE
---

# D3D10DDI_MAPPED_SUBRESOURCE structure


## -description


The D3D10DDI_MAPPED_SUBRESOURCE structure describes a subresource that the driver maps to through a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function.


## -struct-fields




### -field pData

[out] A pointer to a buffer that contains the contents of the subresource.


### -field RowPitch

[out] The row pitch,  width, or physical size (in bytes) of the data.


### -field DepthPitch

[out] The deptch pitch,  width, or physical size (in bytes) of the data.


## -remarks



The <b>pData</b> member points to row 0 and slice 0.

The <b>RowPitch</b> member is the value that is added to <b>pData</b> to move from row to row. Each row should contain multiple pixels.

The <b>DepthPitch</b> member is the value that is added to <b>pData</b> to move from depth slice to depth slice. Each depth slice should contain multiple rows.

It is not advisable to assign a value of zero to the <b>RowPitch</b> and <b>DepthPitch</b> members.

To avoid zero values for these members, it helps to think of all  resources as being three-dimensional, as in these two examples:

<ul>
<li>If the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/details-of-the-extended-format">resource attribute</a> is Buffer or Texture1D and contains  8 bytes, then appropriate values  for <b>RowPitch</b> and <b>DepthPitch</b> would be 8 or more.</li>
<li>If the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/details-of-the-extended-format">resource attribute</a> is Texture2d, even if <b>DepthPitch</b> is not used, <b>DepthPitch</b> must not be assigned a value of zero.</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>
 

 

