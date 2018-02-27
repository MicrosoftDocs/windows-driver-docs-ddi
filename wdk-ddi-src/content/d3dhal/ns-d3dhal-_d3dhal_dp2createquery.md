---
UID: NS:d3dhal._D3DHAL_DP2CREATEQUERY
title: "_D3DHAL_DP2CREATEQUERY"
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2createquery.htm
old-project: display
ms.assetid: 9998743d-57d5-4289-91c5-1c810bf4ca65
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPD3DHAL_DP2CREATEQUERY, D3DHAL_DP2CREATEQUERY, D3DHAL_DP2CREATEQUERY structure [Display Devices], LPD3DHAL_DP2CREATEQUERY, LPD3DHAL_DP2CREATEQUERY structure pointer [Display Devices], _D3DHAL_DP2CREATEQUERY, d3dhal/D3DHAL_DP2CREATEQUERY, d3dhal/LPD3DHAL_DP2CREATEQUERY, d3dstrct_d90487be-ec5e-416b-9ca8-fc431596cb27.xml, display.d3dhal_dp2createquery"
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
-	D3DHAL_DP2CREATEQUERY
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2CREATEQUERY
---

# _D3DHAL_DP2CREATEQUERY structure


## -description



   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2CREATEQUERY structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_CREATEQUERY, and are used to create resources for queries.


## -syntax


````
typedef struct _D3DHAL_DP2CREATEQUERY {
  DWORD        dwQueryID;
  D3DQUERYTYPE QueryType;
} D3DHAL_DP2CREATEQUERY, *LPD3DHAL_DP2CREATEQUERY;
````


## -struct-fields




### -field dwQueryID

Identifies the query.


### -field QueryType

Specifies a value from the D3DQUERYTYPE enumeration that indicates the query capability for which the driver creates resources.


## -remarks



The runtime uses D3DHAL_DP2CREATEQUERY to identify each query with a unique identifier and a query type. The driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2CREATEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and creates resources for the queries that they represent as necessary. 

The driver creates resources for the following query types:

<ul>
<li>
BOOL for D3DQUERYTYPE_EVENT. Before responding with D3DDP2OP_RESPONSEQUERY for an event, the driver must ensure that the graphics processing unit (GPU) is finished processing all <a href="..\d3dhal\ne-d3dhal-_d3dhal_dp2operation.md">D3DHAL_DP2OPERATION</a> operations that are related to the event. That is, the driver only responds after the event's ISSUE_END state occurs. The driver must always set the event's BOOL value to <b>TRUE</b> when responding.

</li>
<li>
DWORD for D3DQUERYTYPE_OCCLUSION. The driver sets this DWORD to the number of pixels for which the z-test passed for all primitives between the begin and end of the query. If the depth buffer is multisampled, the driver determines the number of pixels from the number of samples. However, if the display device is capable of per-multisample z-test accuracy, the conversion to number of pixels should generally be rounded up. An application can then check the occlusion result against 0, to effectively mean "fully occluded". Drivers that convert multisampled quantities to pixel quantities should detect render target multisampling changes and continue to compute the query results appropriately.

</li>
<li>

<a href="..\d3d9types\ns-d3d9types-_d3ddevinfo_vcache.md">D3DDEVINFO_VCACHE</a> structure for D3DQUERYTYPE_VCACHE.

</li>
</ul>



## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_CREATEQUERY



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2deletequery.md">D3DHAL_DP2DELETEQUERY</a>



<a href="..\d3d9types\ns-d3d9types-_d3ddevinfo_vcache.md">D3DDEVINFO_VCACHE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CREATEQUERY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

