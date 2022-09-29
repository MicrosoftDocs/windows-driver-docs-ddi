---
UID: NF:d3dkmthk.D3DKMTSubmitWaitForSyncObjectsToHwQueue
title: D3DKMTSubmitWaitForSyncObjectsToHwQueue function (d3dkmthk.h)
description: Used to submit a wait to the hardware queue.
old-location: display\d3dkmtsubmitwaitforsyncobjectstohwqueue.htm
ms.date: 03/02/2022
keywords: ["D3DKMTSubmitWaitForSyncObjectsToHwQueue function"]
ms.keywords: D3DKMTSubmitWaitForSyncObjectsToHwQueue, D3DKMTSubmitWaitForSyncObjectsToHwQueue function [Display Devices], d3dkmthk/D3DKMTSubmitWaitForSyncObjectsToHwQueue, display.d3dkmtsubmitwaitforsyncobjectstohwqueue
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
 - D3DKMTSubmitWaitForSyncObjectsToHwQueue
 - d3dkmthk/D3DKMTSubmitWaitForSyncObjectsToHwQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTSubmitWaitForSyncObjectsToHwQueue
---

# D3DKMTSubmitWaitForSyncObjectsToHwQueue function

## -description

Used to submit a wait to the hardware queue.

## -parameters

### -param unnamedParam1 [in]

A [D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitwaitforsyncobjectstohwqueue.md) structure holding the information needed to submit a wait to the hardware queue.

## -returns

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The device context was called successfully. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitwaitforsyncobjectstohwqueue.md)
