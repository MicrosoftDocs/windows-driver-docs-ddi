---
UID: NS:d3dhal._D3DHAL_DP2SETINDICES
title: "_D3DHAL_DP2SETINDICES"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2SETINDICES structure is used to set the current index buffer for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setindices.htm
old-project: display
ms.assetid: ac1b7daf-803d-48a0-89de-4a438f3837f9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DP2SETINDICES, D3DHAL_DP2SETINDICES, D3DHAL_DP2SETINDICES structure [Display Devices], LPD3DHAL_DP2SETINDICES, LPD3DHAL_DP2SETINDICES structure pointer [Display Devices], _D3DHAL_DP2SETINDICES, d3dhal/D3DHAL_DP2SETINDICES, d3dhal/LPD3DHAL_DP2SETINDICES, d3dstrct_fd1eb5e4-28c8-45f9-90ba-b57970888717.xml, display.d3dhal_dp2setindices"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DHAL_DP2SETINDICES
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETINDICES
---

# _D3DHAL_DP2SETINDICES structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2SETINDICES structure is used to set the current index buffer for <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwVBHandle

Specifies the surface handle associated with this surface through a call to <a href="https://msdn.microsoft.com/dd07e49c-ec1f-4ba6-8b17-80ce6d3c5813">D3dCreateSurfaceEx</a>.


### -field dwStride

Specifies the size of the indices contained in the index buffer and has the value 2 if the indices are 16-bit, or 4 if the indices are 32-bit quantities.


## -remarks



A handle value of zero is valid and indicates that the current index buffer is cleared. Subsequent attempts to draw indexed primitives (before a new current index buffer is established via another D3DDP2OP_SETINDICES token) should be handled by the driver such that a crash does not occur. The debug version of your driver should display informative messages to the debug output stream when this error condition is detected.




## -see-also




<a href="https://msdn.microsoft.com/dd07e49c-ec1f-4ba6-8b17-80ce6d3c5813">D3dCreateSurfaceEx</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

