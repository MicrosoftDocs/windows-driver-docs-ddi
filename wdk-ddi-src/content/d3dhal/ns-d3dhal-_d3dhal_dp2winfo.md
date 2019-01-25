---
UID: NS:d3dhal._D3DHAL_DP2WINFO
title: "_D3DHAL_DP2WINFO" (d3dhal.h)
description: The D3DHAL_DP2WINFO structure is used to inform the driver of the w-range to be used for w-buffering.
old-location: display\d3dhal_dp2winfo.htm
tech.root: display
ms.assetid: da4cdaff-4418-4b88-bf47-5a1567e940e1
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2WINFO, D3DHAL_DP2WINFO, D3DHAL_DP2WINFO structure [Display Devices], LPD3DHAL_DP2WINFO, LPD3DHAL_DP2WINFO structure pointer [Display Devices], _D3DHAL_DP2WINFO, d3dhal/D3DHAL_DP2WINFO, d3dhal/LPD3DHAL_DP2WINFO, d3dstrct_f0755102-ab0f-43fd-9821-3cde940d24a1.xml, display.d3dhal_dp2winfo"
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2WINFO
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2WINFO
---

# _D3DHAL_DP2WINFO structure


## -description


The D3DHAL_DP2WINFO structure is used to inform the driver of the w-range to be used for w-buffering.


## -struct-fields




### -field dvWNear


### -field dvWFar

Specify the near and far limit of the w-buffer, respectively. These members can be any valid floating-point values.


## -remarks



The <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback parses a D3DHAL_DP2WINFO structure from the command buffer and updates the driver's scaling parameters for w-buffering when <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> is set to D3DDP2OP_WINFO.

One D3DHAL_DP2WINFO structure follows the D3DHAL_DP2COMMAND structure in the command buffer.

The driver should update the w-buffer portion of its internal rendering context with the w-ranges specified in this structure. The driver can use this information to scale the w-buffer.

Video adapters that do not support this feature should ignore and skip over these instructions and continue processing the rest of the command buffer.




## -see-also




D3DDP2OP_WINFO



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

