---
UID: NF:d3dkmthk.D3DKMTDestroyHwContext
title: D3DKMTDestroyHwContext function (d3dkmthk.h)
description: Used to destroy a hardware context.
old-location: display\d3dkmtdestroyhwcontext.htm
ms.date: 02/23/2022
keywords: ["D3DKMTDestroyHwContext function"]
ms.keywords: D3DKMTDestroyHwContext, D3DKMTDestroyHwContext function [Display Devices], d3dkmthk/D3DKMTDestroyHwContext, display.d3dkmtdestroyhwcontext
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
 - D3DKMTDestroyHwContext
 - d3dkmthk/D3DKMTDestroyHwContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTDestroyHwContext
---

# D3DKMTDestroyHwContext function

## -description

Used to destroy a hardware context.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_DESTROYHWCONTEXT](ns-d3dkmthk-_d3dkmt_destroyhwcontext.md) structure holding the information needed to destroy a hardware context.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -see-also

[D3DKMT_DESTROYHWCONTEXT](ns-d3dkmthk-_d3dkmt_destroyhwcontext.md)
