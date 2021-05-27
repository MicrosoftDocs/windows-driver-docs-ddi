---
UID: NF:mdlapi.NdisFreeMdl
title: NdisFreeMdl
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdisFreeMdl function frees an MDL that was allocated by calling the NdisAllocateMdl function.
tech.root: netvista 
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateMdl
req.dll: 
req.header: ndis/mdlapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: Ndis.lib
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - mdlapi.h
api_name:
 - NdisFreeMdl
f1_keywords:
 - NdisFreeMdl
 - mdlapi/NdisFreeMdl
dev_langs:
 - c++
---

# NdisFreeMdl function


## -description

The 
  <b>NdisFreeMdl</b> function frees an MDL that was allocated by calling the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a> function.

## -parameters

### -param Mdl 

[in]
A pointer to the MDL that NDIS should free.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a>

