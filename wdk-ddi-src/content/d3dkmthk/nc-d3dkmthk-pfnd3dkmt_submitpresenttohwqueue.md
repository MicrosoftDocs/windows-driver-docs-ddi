---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITPRESENTTOHWQUEUE
title: PFND3DKMT_SUBMITPRESENTTOHWQUEUE (d3dkmthk.h)
description: pfnSubmitPresentToHwQueueCb is invoked by user mode drivers to submit a Blt Present operation to a hardware queue.
ms.assetid: 7973174e-6d3d-4fa2-8a91-ab1d03e348b4
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SUBMITPRESENTTOHWQUEUE"
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_SUBMITPRESENTTOHWQUEUE
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5, 19H1
---

# PFND3DKMT_SUBMITPRESENTTOHWQUEUE callback function

## -description

pfnSubmitPresentToHwQueueCb is invoked by user mode drivers to submit a Blt Present operation to a hardware queue. This callback replaces [pfnPresentCb](../d3dumddi/nc-d3dumddi-pfnd3dddi_presentcb.md) in WDDM 2.0-2.3.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITPRESENTTOHWQUEUE Pfnd3dkmtSubmitpresenttohwqueue; 

// Definition

NTSTATUS Pfnd3dkmtSubmitpresenttohwqueue 
(
	CONST D3DKMT_SUBMITPRESENTTOHWQUEUE *
)
{...}

```

## -parameters

### -param *

Pointer to a [D3DKMT_SUBMITPRESENTTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitpresenttohwqueue.md) structure.

## -returns

Returns NTSTATUS.

## -remarks



## -see-also
