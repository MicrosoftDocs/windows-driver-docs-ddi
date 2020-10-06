---
UID: NS:d3dumddi._D3DDDI_ISSUEQUERYFLAGS
title: _D3DDDI_ISSUEQUERYFLAGS (d3dumddi.h)
description: The D3DDDI_ISSUEQUERYFLAGS structure identifies the state of a query issue.
old-location: display\d3dddi_issuequeryflags.htm
tech.root: display
ms.assetid: 68360c2e-4b03-40a3-a313-bdb9ef26a298
ms.date: 05/10/2018
keywords: ["D3DDDI_ISSUEQUERYFLAGS structure"]
ms.keywords: D3DDDI_ISSUEQUERYFLAGS, D3DDDI_ISSUEQUERYFLAGS structure [Display Devices], D3D_other_Structs_794dd0b0-f24c-4e9e-befe-d79dd4efbaef.xml, _D3DDDI_ISSUEQUERYFLAGS, d3dumddi/D3DDDI_ISSUEQUERYFLAGS, display.d3dddi_issuequeryflags
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
targetos: Windows
req.typenames: D3DDDI_ISSUEQUERYFLAGS
f1_keywords:
 - _D3DDDI_ISSUEQUERYFLAGS
 - d3dumddi/_D3DDDI_ISSUEQUERYFLAGS
 - D3DDDI_ISSUEQUERYFLAGS
 - d3dumddi/D3DDDI_ISSUEQUERYFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDI_ISSUEQUERYFLAGS
---

# _D3DDDI_ISSUEQUERYFLAGS structure


## -description

The D3DDDI_ISSUEQUERYFLAGS structure identifies the state of a query issue.

## -struct-fields

### -field Begin

A UINT value that specifies whether to start the query issue. The Microsoft Direct3D runtime does not request query data while in this state.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field End

A UINT value that specifies whether to end the query issue and transition the state to subsignaled. Results of the query are not available until the state transitions to signaled.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that is contained in D3DDDI_ISSUEQUERYFLAGS that can hold one 32-bit value that identifies the state of the query.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_issuequery">D3DDDIARG_ISSUEQUERY</a>