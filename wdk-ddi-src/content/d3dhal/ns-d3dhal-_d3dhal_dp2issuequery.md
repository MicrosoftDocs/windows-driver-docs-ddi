---
UID: NS:d3dhal._D3DHAL_DP2ISSUEQUERY
title: "_D3DHAL_DP2ISSUEQUERY"
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2issuequery.htm
old-project: display
ms.assetid: e7870f7a-545e-43eb-99c5-42a740585c43
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2ISSUEQUERY, D3DHAL_DP2ISSUEQUERY, D3DHAL_DP2ISSUEQUERY structure [Display Devices], LPD3DHAL_DP2ISSUEQUERY, LPD3DHAL_DP2ISSUEQUERY structure pointer [Display Devices], _D3DHAL_DP2ISSUEQUERY, d3dhal/D3DHAL_DP2ISSUEQUERY, d3dhal/LPD3DHAL_DP2ISSUEQUERY, d3dstrct_bc6a2c98-b3cf-4161-8aca-fadda2a6cceb.xml, display.d3dhal_dp2issuequery"
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
-	D3DHAL_DP2ISSUEQUERY
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2ISSUEQUERY
---

# _D3DHAL_DP2ISSUEQUERY structure


## -description



   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2ISSUEQUERY structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_ISSUEQUERY, and are used to query for various types of information.


## -syntax


````
typedef struct _D3DHAL_DP2ISSUEQUERY {
  DWORD dwQueryID;
  DWORD dwFlags;
} D3DHAL_DP2ISSUEQUERY, *LPD3DHAL_DP2ISSUEQUERY;
````


## -struct-fields




### -field dwQueryID

Identifies the query for which the driver asynchronously provides information.


### -field dwFlags

Specifies the state of the query. This member can contain one or more of the following flags: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>

<dl>
<dt>D3DISSUE_BEGIN</dt>
<dt>(1 &lt;&lt; 1)</dt>
</dl>


</td>
<td>
Starts building the query. The runtime does not request query data while in this state.

</td>
</tr>
<tr>
<td>

<dl>
<dt>D3DISSUE_END</dt>
<dt>(1 &lt;&lt; 0)</dt>
</dl>


</td>
<td>
Transitions the state to subsignaled. Results of the query are not available until the state transitions to signaled.

</td>
</tr>
</table>
 

The driver can ignore query requests with <b>dwFlags</b> set to 0. 


## -remarks



The runtime uses D3DHAL_DP2ISSUEQUERY to identify each query that the driver must process. The driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2ISSUEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and retrieves information associated with the queries that they represent. 




## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2responsequery.md">D3DHAL_DP2RESPONSEQUERY</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2createquery.md">D3DHAL_DP2CREATEQUERY</a>



D3DDP2OP_ISSUEQUERY



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


