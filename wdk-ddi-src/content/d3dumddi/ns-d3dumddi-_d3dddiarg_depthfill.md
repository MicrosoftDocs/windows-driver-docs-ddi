---
UID: NS:d3dumddi._D3DDDIARG_DEPTHFILL
title: _D3DDDIARG_DEPTHFILL (d3dumddi.h)
description: The D3DDDIARG_DEPTHFILL structure describes the parameters of a depth-fill operation.
old-location: display\d3dddiarg_depthfill.htm
tech.root: display
ms.assetid: e4070d53-bdd6-4708-857d-7ed1e9699e21
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DEPTHFILL, D3DDDIARG_DEPTHFILL structure [Display Devices], UMDisplayDriver_param_Structs_94ba7961-5956-4939-830f-eaa15aeca614.xml, _D3DDDIARG_DEPTHFILL, d3dumddi/D3DDDIARG_DEPTHFILL, display.d3dddiarg_depthfill
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDIARG_DEPTHFILL
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DEPTHFILL
---

# _D3DDDIARG_DEPTHFILL structure


## -description


The D3DDDIARG_DEPTHFILL structure describes the parameters of a depth-fill operation. 


## -struct-fields




### -field hResource

[in] A handle to the resource.


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or buffer, on which a rectangular area is depth-filled.


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the buffer to depth fill. 


### -field Depth

A pixel value that is specified in native format for the fill depth. 


## -see-also




<a href="https://msdn.microsoft.com/fc889cc0-d71d-4a81-8fa5-894c676ac110">DepthFill</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a>
 

 

