---
UID: NS:d3dkmthk._D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
title: _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY (d3dkmthk.h)
description: A structure that holds information to query the physical adapter PNP key.
old-location: display\d3dkmt_query_physical_adapter_pnp_key.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure"]
ms.keywords: D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY, D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure [Display Devices], _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY, d3dkmthk/D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY, display.d3dkmt_query_physical_adapter_pnp_key
req.header: d3dkmthk.h
req.include-header: 
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
tech.root: display
req.typenames: D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
f1_keywords:
 - _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - d3dkmthk/_D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - d3dkmthk/D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
---

# _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure


## -description

A structure that holds information to query the physical adapter PNP key.

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field PnPKeyType

The type of the PNP key being queried.

### -field pDest

A WCHAR value respresenting the pDest.

### -field pCchDest

A UINT value representing the pCchDest.

