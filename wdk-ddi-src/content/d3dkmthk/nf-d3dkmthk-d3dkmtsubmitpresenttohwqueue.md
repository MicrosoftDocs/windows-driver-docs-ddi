---
UID: NF:d3dkmthk.D3DKMTSubmitPresentToHwQueue
title: D3DKMTSubmitPresentToHwQueue function (d3dkmthk.h)
description: SubmitPresentToHwQueue submits a Blt Present operation to a hardware queue.
ms.assetid: d43c7da0-ce52-408c-8b74-5941ecde7898
ms.date: 10/19/2018
keywords: ["D3DKMTSubmitPresentToHwQueue function"]
f1_keywords:
 - "d3dkmthk/D3DKMTSubmitPresentToHwQueue"
 - "D3DKMTSubmitPresentToHwQueue"
ms.keywords: D3DKMTSubmitPresentToHwQueue
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
- DllExport
api_location: 
- Gdi32.dll
api_name: 
- D3DKMTSubmitPresentToHwQueue
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3DKMTSubmitPresentToHwQueue function


## -description

> [NOTE!] 
> This function has been deprecated, and replaced with the D3DKMTSubmitPresentBltToHwQueue function.

SubmitPresentToHwQueue submits a Blt Present operation to a hardware queue.

## -parameters

### -param Arg1

[in,out] Pointer to a [D3DKMT_SUBMITPRESENTTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitpresenttohwqueue.md) structure.

## -returns


This function returns NTSTATUS.


## -remarks

## -see-also
