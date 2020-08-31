---
UID: NS:d3dhal._D3DHAL_DP2ISSUEQUERY
title: _D3DHAL_DP2ISSUEQUERY (d3dhal.h)
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2issuequery.htm
tech.root: display
ms.assetid: e7870f7a-545e-43eb-99c5-42a740585c43
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2ISSUEQUERY structure"]
ms.keywords: "*LPD3DHAL_DP2ISSUEQUERY, D3DHAL_DP2ISSUEQUERY, D3DHAL_DP2ISSUEQUERY structure [Display Devices], LPD3DHAL_DP2ISSUEQUERY, LPD3DHAL_DP2ISSUEQUERY structure pointer [Display Devices], _D3DHAL_DP2ISSUEQUERY, d3dhal/D3DHAL_DP2ISSUEQUERY, d3dhal/LPD3DHAL_DP2ISSUEQUERY, d3dstrct_bc6a2c98-b3cf-4161-8aca-fadda2a6cceb.xml, display.d3dhal_dp2issuequery"
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
targetos: Windows
req.typenames: D3DHAL_DP2ISSUEQUERY
f1_keywords:
 - _D3DHAL_DP2ISSUEQUERY
 - d3dhal/_D3DHAL_DP2ISSUEQUERY
 - D3DHAL_DP2ISSUEQUERY
 - d3dhal/D3DHAL_DP2ISSUEQUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2ISSUEQUERY
---

# _D3DHAL_DP2ISSUEQUERY structure


## -description

   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2ISSUEQUERY structures are parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_ISSUEQUERY, and are used to query for various types of information.

## -struct-fields

### -field dwQueryID

Identifies the query for which the driver asynchronously provides information.

### -field dwFlags

Specifies the state of the query. This member can contain one or more of the following flags: 

|Value|Meaning|
|---|---|
|D3DISSUE_BEGIN (1 << 1)|Starts building the query. The runtime does not request query data while in this state.|
|D3DISSUE_END (1 << 0)|Transitions the state to subsignaled. Results of the query are not available until the state transitions to signaled.|
 

The driver can ignore query requests with **dwFlags** set to 0.

## -remarks

The runtime uses D3DHAL_DP2ISSUEQUERY to identify each query that the driver must process. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2ISSUEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and retrieves information associated with the queries that they represent.

## -see-also

D3DDP2OP_ISSUEQUERY



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2createquery">D3DHAL_DP2CREATEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2responsequery">D3DHAL_DP2RESPONSEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>

