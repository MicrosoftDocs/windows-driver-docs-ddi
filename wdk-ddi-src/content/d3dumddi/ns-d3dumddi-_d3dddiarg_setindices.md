---
UID: NS:d3dumddi._D3DDDIARG_SETINDICES
title: "_D3DDDIARG_SETINDICES"
author: windows-driver-content
description: The D3DDDIARG_SETINDICES structure describes parameters for setting the current index buffer.
old-location: display\d3dddiarg_setindices.htm
old-project: display
ms.assetid: 9a0b8706-91ba-42a5-aaa2-0381931d64f0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDIARG_SETINDICES, D3DDDIARG_SETINDICES structure [Display Devices], UMDisplayDriver_param_Structs_68458ee2-76c8-41c5-b610-47ef40874c1e.xml, _D3DDDIARG_SETINDICES, d3dumddi/D3DDDIARG_SETINDICES, display.d3dddiarg_setindices
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_SETINDICES
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETINDICES
---

# _D3DDDIARG_SETINDICES structure


## -description


The D3DDDIARG_SETINDICES structure describes parameters for setting the current index buffer. 


## -struct-fields




### -field hIndexBuffer

[in] A handle to the surface that is associated with the index buffer.


### -field Stride

[in] The size, in bytes, of the indices that are contained in the index buffer. The value of this member is 2 if the indices are 16-bit quantities or 4 if the indices are 32-bit quantities.


## -see-also




<a href="https://msdn.microsoft.com/5348b3f9-78c5-4915-ba68-296d6f9f916c">SetIndices</a>



<a href="https://msdn.microsoft.com/75a70801-0338-45ed-a691-5f84202575d5">SetStreamSourceUM</a>
 

 

