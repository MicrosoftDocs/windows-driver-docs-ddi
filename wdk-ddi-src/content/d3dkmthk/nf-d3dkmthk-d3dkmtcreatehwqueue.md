---
UID: NF:d3dkmthk.D3DKMTCreateHwQueue
title: D3DKMTCreateHwQueue function (d3dkmthk.h)
description: Learn more about the D3DKMTCreateHwQueue function.
ms.date: 03/21/2024
keywords: ["D3DKMTCreateHwQueue function"]
req.header: d3dkmthk.h
req.construct-type: function
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTCreateHwQueue
 - d3dkmthk/D3DKMTCreateHwQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTCreateHwQueue
---

# D3DKMTCreateHwQueue function (d3dkmthk.h)



## -description

*Dxgkrnl* calls **D3DKMTCreateHwQueue** to create a new hardware queue.

## -parameters

### -param unnamedParam1

[in/out] Pointer to a [**D3DKMT_CREATEHWQUEUE**](ns-d3dkmthk-_d3dkmt_createhwqueue.md) structure that describes the hardware queue to create.

## -returns

**D3DKMTCreateHwQueue** returns STATUS_SUCCESS upon successful completion. Otherwise, it returns an appropriate NSTATUS code.
