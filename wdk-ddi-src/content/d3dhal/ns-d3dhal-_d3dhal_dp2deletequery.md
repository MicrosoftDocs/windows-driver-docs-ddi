---
UID: NS:d3dhal._D3DHAL_DP2DELETEQUERY
title: "_D3DHAL_DP2DELETEQUERY"
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2deletequery.htm
old-project: display
ms.assetid: c125e21f-20be-42c1-ba24-b13f2475f02e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*LPD3DHAL_DP2DELETEQUERY, D3DHAL_DP2DELETEQUERY, D3DHAL_DP2DELETEQUERY structure [Display Devices], LPD3DHAL_DP2DELETEQUERY, LPD3DHAL_DP2DELETEQUERY structure pointer [Display Devices], _D3DHAL_DP2DELETEQUERY, d3dhal/D3DHAL_DP2DELETEQUERY, d3dhal/LPD3DHAL_DP2DELETEQUERY, d3dstrct_3194de0d-21ee-4f44-9be3-2f2ebe6b06e2.xml, display.d3dhal_dp2deletequery"
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
-	D3DHAL_DP2DELETEQUERY
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2DELETEQUERY
---

# _D3DHAL_DP2DELETEQUERY structure


## -description



   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2DELETEQUERY structures are parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DELETEQUERY, and are used to release resources for queries.


## -struct-fields




### -field dwQueryID

Identifies the query for which the driver releases resources.


## -remarks



The runtime uses D3DHAL_DP2DELETEQUERY to identify each query. The driver's <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2DELETEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and releases resources for the queries that they represent. 




## -see-also




D3DDP2OP_DELETEQUERY



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545469">D3DHAL_DP2CREATEQUERY</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

