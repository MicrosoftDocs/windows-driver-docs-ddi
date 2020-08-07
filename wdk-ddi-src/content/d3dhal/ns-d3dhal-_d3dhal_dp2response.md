---
UID: NS:d3dhal._D3DHAL_DP2RESPONSE
title: _D3DHAL_DP2RESPONSE (d3dhal.h)
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2response.htm
tech.root: display
ms.assetid: 3a8ae2a9-21cd-4b0d-b293-60865a4fdfe6
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2RESPONSE structure"]
ms.keywords: "*LPD3DHAL_DP2RESPONSE, D3DHAL_DP2RESPONSE, D3DHAL_DP2RESPONSE structure [Display Devices], LPD3DHAL_DP2RESPONSE, LPD3DHAL_DP2RESPONSE structure pointer [Display Devices], _D3DHAL_DP2RESPONSE, d3dhal/D3DHAL_DP2RESPONSE, d3dhal/LPD3DHAL_DP2RESPONSE, d3dstrct_cd629a64-c8e9-45d2-a0bc-048ff623cc97.xml, display.d3dhal_dp2response"
f1_keywords:
 - "d3dhal/D3DHAL_DP2RESPONSE"
 - "D3DHAL_DP2RESPONSE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2RESPONSE
targetos: Windows
req.typenames: D3DHAL_DP2RESPONSE, *LPD3DHAL_DP2RESPONSE
---

# _D3DHAL_DP2RESPONSE structure


## -description



   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2RESPONSE structures are parsed from the response buffer that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback returns to the runtime. Each structure specifies the availability of responses to previously issued queries.


## -struct-fields




### -field bCommand

Specifies a response token. This member can be either D3DDP2OP_RESPONSECONTINUE or D3DDP2OP_RESPONSEQUERY of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ne-d3dhal-_d3dhal_dp2operation">D3DHAL_DP2OPERATION</a> enumerated type. 


### -field bReserved

Reserved for system use and should be ignored by the driver.


### -field wStateCount

Specifies the number of responses (that is, the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2responsequery">D3DHAL_DP2RESPONSEQUERY</a> structures) that follow this D3DHAL_DP2RESPONSE structure. If the driver sets <b>bCommand</b> to D3DDP2OP_RESPONSECONTINUE, the driver should set this member to zero. However, the runtime ignores this member when <b>bCommand</b> is set to D3DDP2OP_RESPONSECONTINUE; this member is only valid when the driver sets <b>bCommand</b> to D3DDP2OP_RESPONSEQUERY. 


### -field dwTotalSize

Specifies the total size, in bytes, of the responses associated with this D3DHAL_DP2RESPONSE structure. The driver also includes the size of this D3DHAL_DP2RESPONSE structure in the total size to let the runtime skip over this D3DHAL_DP2RESPONSE structure when parsing the response buffer. 


## -see-also




D3DDP2OP_RESPONSECONTINUE



D3DDP2OP_RESPONSEQUERY



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ne-d3dhal-_d3dhal_dp2operation">D3DHAL_DP2OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2responsequery">D3DHAL_DP2RESPONSEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

