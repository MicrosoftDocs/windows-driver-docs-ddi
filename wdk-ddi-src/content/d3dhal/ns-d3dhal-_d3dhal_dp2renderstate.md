---
UID: NS:d3dhal._D3DHAL_DP2RENDERSTATE
title: _D3DHAL_DP2RENDERSTATE (d3dhal.h)
description: One or more D3DHAL_DP2RENDERSTATE structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_RENDERSTATE, and are used to set the appropriate render state.
old-location: display\d3dhal_dp2renderstate.htm
tech.root: display
ms.assetid: 9d30ed5d-0621-4a90-941c-c5b0564df13f
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2RENDERSTATE, D3DHAL_DP2RENDERSTATE, D3DHAL_DP2RENDERSTATE structure [Display Devices], LPD3DHAL_DP2RENDERSTATE, LPD3DHAL_DP2RENDERSTATE structure pointer [Display Devices], _D3DHAL_DP2RENDERSTATE, d3dhal/D3DHAL_DP2RENDERSTATE, d3dhal/LPD3DHAL_DP2RENDERSTATE, d3dstrct_4cfe9ea2-c3cc-432d-bd11-85d51ba121b5.xml, display.d3dhal_dp2renderstate"
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
-	D3DHAL_DP2RENDERSTATE
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2RENDERSTATE
---

# _D3DHAL_DP2RENDERSTATE structure


## -description


One or more D3DHAL_DP2RENDERSTATE structures are parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_RENDERSTATE, and are used to set the appropriate render state.


## -struct-fields




### -field RenderState

Specifies a D3DRENDERSTATETYPE enumerated type that indicates the render state to be updated. Render states that are requested at the application level are described in the DirectX SDK documentation. Render states that are exclusively used by drivers are described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a>.


### -field dvState

Specifies the value that the driver should update the render state identified by the <b>RenderState</b> member with. This member is valid when <b>RenderState</b> requires a D3DVALUE. 


### -field dwState

Specifies the value that the driver should update the render state identified by <b>RenderState</b> to. This member is valid when <b>RenderState</b> requires a DWORD.


## -remarks




<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should process <b>wStateCount</b> D3DHAL_DP2RENDERSTATE structures from the command buffer. The value of <b>wStateCount</b> is specified in the D3DHAL_DP2COMMAND structure.

For each D3DHAL_DP2RENDERSTATE structure, <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should update the driver's private render state and the render state array that the <b>lpdwRStates</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a> points to. The element to be updated in the public render state array is <b>lpdwRStates[RenderState]</b>.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures. The driver should update <b>lpdwRStates</b>[D3DRENDERSTATE_FILLMODE] to be D3DFILL_SOLID and <b>lpdwRStates</b>[D3DRENDERSTATE_SHADEMODE] to be D3DSHADE_GOURAUD. The driver should also update its private state accordingly.

<img alt="Figure showing a command buffer with a D3DDP2OP_RENDERSTATE command and two D3DHAL_DP2RENDERSTATE structures" src="images/dp2rs.png"/>
Although render states whose values are Boolean in type are documented as only accepting <b>TRUE</b>(1) and <b>FALSE</b>(0) the runtime does not validate this and accepts any subzero value as true. The sample driver interprets this strictly and does interpret values other than 1 as being <b>TRUE</b>. However, because the runtime does not offer validation, your driver should interpret 0 as <b>FALSE</b> and any other subzero value as <b>TRUE</b>. In this respect your driver should not mimic the behavior of the supplied sample driver.




## -see-also




D3DDP2OP_RENDERSTATE



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

