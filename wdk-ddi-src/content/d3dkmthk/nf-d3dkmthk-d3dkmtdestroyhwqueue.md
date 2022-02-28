---
UID: NF:d3dkmthk.D3DKMTDestroyHwQueue
title: D3DKMTDestroyHwQueue function (d3dkmthk.h)
description: Used to destroy a hardware queue.
old-location: display\d3dkmtdestroyhwqueue.htm
ms.date: 02/23/2022
keywords: ["D3DKMTDestroyHwQueue function"]
ms.keywords: D3DKMTDestroyHwQueue, D3DKMTDestroyHwQueue function [Display Devices], d3dkmthk/D3DKMTDestroyHwQueue, display.d3dkmtdestroyhwqueue
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTDestroyHwQueue
 - d3dkmthk/D3DKMTDestroyHwQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTDestroyHwQueue
---

# D3DKMTDestroyHwQueue function

## -description

Used to destroy a hardware queue.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_DESTROYHWQUEUE](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md) structure holding the information needed to destroy a hardware queue.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -see-also

[D3DKMT_DESTROYHWQUEUE](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md)
