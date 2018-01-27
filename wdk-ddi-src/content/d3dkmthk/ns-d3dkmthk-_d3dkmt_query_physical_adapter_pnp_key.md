---
UID: NS:d3dkmthk._D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
title: _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
author: windows-driver-content
description: A structure that holds information to query the physical adapter PNP key.
old-location: display\d3dkmt_query_physical_adapter_pnp_key.htm
old-project: display
ms.assetid: 58E5D200-56C3-48BA-A7C9-C9DC01592554
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_query_physical_adapter_pnp_key, d3dkmthk/D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY, D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure [Display Devices], D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY, _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmthk.h
apiname: 
-	D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
---

# _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure


## -description


A structure that holds information to query the physical adapter PNP key.


## -syntax


````
typedef struct _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY {
  UINT                PhysicalAdapterIndex;
  D3DKMT_PNP_KEY_TYPE PnPKeyType;
  WCHAR               *pDest;
   UINT               *pCchDest;
} D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY;
````


## -struct-fields




### -field PhysicalAdapterIndex

The physical adapter index.


### -field PnPKeyType

The type of the PNP key being queried.


### -field pDest

A WCHAR value respresenting the pDest.


### -field pCchDest

A UINT value representing the pCchDest.

