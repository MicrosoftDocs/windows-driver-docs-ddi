---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITPRESENTTOHWQUEUE
title: PFND3DKMT_SUBMITPRESENTTOHWQUEUE (d3dkmthk.h)
description: The PFND3DKMT_SUBMITPRESENTTOHWQUEUE callback function is invoked by user mode drivers to submit a Blt Present operation to a hardware queue.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SUBMITPRESENTTOHWQUEUE callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5, 19H1
f1_keywords:
 - PFND3DKMT_SUBMITPRESENTTOHWQUEUE
 - d3dkmthk/PFND3DKMT_SUBMITPRESENTTOHWQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SUBMITPRESENTTOHWQUEUE
dev_langs:
 - c++
---

# PFND3DKMT_SUBMITPRESENTTOHWQUEUE callback function


## -description

pfnSubmitPresentToHwQueueCb is invoked by user mode drivers to submit a Blt Present operation to a hardware queue. This callback replaces [pfnPresentCb](../d3dumddi/nc-d3dumddi-pfnd3dddi_presentcb.md) in WDDM 2.0-2.3.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_SUBMITPRESENTTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitpresenttohwqueue.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

