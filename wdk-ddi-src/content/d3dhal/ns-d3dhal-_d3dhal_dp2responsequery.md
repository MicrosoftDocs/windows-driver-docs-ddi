---
UID: NS:d3dhal._D3DHAL_DP2RESPONSEQUERY
title: "_D3DHAL_DP2RESPONSEQUERY"
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2responsequery.htm
old-project: display
ms.assetid: fda36df2-d346-47a5-b391-dd4509446ca1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2RESPONSEQUERY, D3DHAL_DP2RESPONSEQUERY, D3DHAL_DP2RESPONSEQUERY structure [Display Devices], LPD3DHAL_DP2RESPONSEQUERY, LPD3DHAL_DP2RESPONSEQUERY structure pointer [Display Devices], _D3DHAL_DP2RESPONSEQUERY, d3dhal/D3DHAL_DP2RESPONSEQUERY, d3dhal/LPD3DHAL_DP2RESPONSEQUERY, d3dstrct_6164398f-06cc-4d18-8793-8dbbbdd63b40.xml, display.d3dhal_dp2responsequery"
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
-	D3DHAL_DP2RESPONSEQUERY
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2RESPONSEQUERY
---

# _D3DHAL_DP2RESPONSEQUERY structure


## -description



   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2RESPONSEQUERY structure are parsed from the response buffer by the runtime after the runtime calls the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback. The driver sets the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545710">D3DHAL_DP2RESPONSE</a> structure's <b>bCommand</b> member to D3DDP2OP_RESPONSEQUERY to indicate that responses to previously issued queries are available in the response buffer. 


## -struct-fields




### -field dwQueryID

Identifies the query for which response data is available.


### -field dwSize

Specifies the size, in bytes, of the query information that the driver returns to the runtime.


## -remarks



The runtime uses the D3DDP2OP_ISSUEQUERY command to request that the driver process queries. The driver's <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback should process <b>wPrimitiveCount </b><a href="https://msdn.microsoft.com/library/windows/hardware/ff545638">D3DHAL_DP2ISSUEQUERY</a> query structures from the command buffer. The value of <b>wPrimitiveCount </b> is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure. The driver parses these query structures and translates them to its hardware specific commands. 

If previously submitted queries using the D3DDP2OP_ISSUEQUERY operation completed, the driver sets the size of the response buffer in the dwErrorOffset member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a> structure and sets the <b>ddrval</b> member of D3DHAL_DRAWPRIMITIVES2DATA to D3D_OK for successful completion. The driver also overwrites the incoming command buffer with the outgoing response buffer. Each D3DHAL_DP2RESPONSEQUERY in the response buffer is followed by the following data related to the query: 

<ul>
<li>
BOOL for D3DQUERYTYPE_EVENT. Before responding with D3DDP2OP_RESPONSEQUERY for an event, the driver must ensure that the graphics processing unit (GPU) is finished processing all <a href="https://msdn.microsoft.com/library/windows/hardware/ff545678">D3DHAL_DP2OPERATION</a> operations that are related to the event. That is, the driver only responds after the event's ISSUE_END state occurs. The driver must always set the event's BOOL value to <b>TRUE</b> when responding.

</li>
<li>
DWORD for D3DQUERYTYPE_OCCLUSION. The driver sets this DWORD to the number of pixels for which the z-test passed for all primitives between the begin and end of the query. If the depth buffer is multisampled, the driver determines the number of pixels from the number of samples. However, if the display device is capable of per-multisample z-test accuracy, the conversion to number of pixels should generally be rounded up. An application can then check the occlusion result against 0, to effectively mean "fully occluded". Drivers that convert multisampled quantities to pixel quantities should detect render target multisampling changes and continue to compute the query results appropriately.

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544702">D3DDEVINFO_VCACHE</a> structure for D3DQUERYTYPE_VCACHE.

</li>
</ul>
The runtime parses the returned response buffer and updates its internal data structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544702">D3DDEVINFO_VCACHE</a>



D3DDP2OP_ISSUEQUERY



D3DDP2OP_RESPONSEQUERY



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545638">D3DHAL_DP2ISSUEQUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545710">D3DHAL_DP2RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

