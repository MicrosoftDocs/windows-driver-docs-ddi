---
UID: NS:d3d10umddi.D3D10DDI_MAPPED_SUBRESOURCE
title: D3D10DDI_MAPPED_SUBRESOURCE
author: windows-driver-content
description: The D3D10DDI_MAPPED_SUBRESOURCE structure describes a subresource that the driver maps to through a call to the driver's ResourceMap function.
old-location: display\d3d10ddi_mapped_subresource.htm
old-project: display
ms.assetid: a55f9aee-c6a5-4391-aad1-4003e58692cd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDI_MAPPED_SUBRESOURCE, D3D10DDI_MAPPED_SUBRESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_19502bf4-94a6-48d5-8294-c058c254540f.xml, d3d10umddi/D3D10DDI_MAPPED_SUBRESOURCE, display.d3d10ddi_mapped_subresource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDI_MAPPED_SUBRESOURCE
product: Windows
targetos: Windows
req.typenames: D3D10DDI_MAPPED_SUBRESOURCE
---

# D3D10DDI_MAPPED_SUBRESOURCE structure


## -description


The D3D10DDI_MAPPED_SUBRESOURCE structure describes a subresource that the driver maps to through a call to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function.


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
<li>If the <a href="https://msdn.microsoft.com/e9cd2bc7-99c1-4aca-91b0-9faefa4a856d">resource attribute</a> is Buffer or Texture1D and contains  8 bytes, then appropriate values  for <b>RowPitch</b> and <b>DepthPitch</b> would be 8 or more.</li>
<li>If the <a href="https://msdn.microsoft.com/e9cd2bc7-99c1-4aca-91b0-9faefa4a856d">resource attribute</a> is Texture2d, even if <b>DepthPitch</b> is not used, <b>DepthPitch</b> must not be assigned a value of zero.</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDI_MAPPED_SUBRESOURCE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

