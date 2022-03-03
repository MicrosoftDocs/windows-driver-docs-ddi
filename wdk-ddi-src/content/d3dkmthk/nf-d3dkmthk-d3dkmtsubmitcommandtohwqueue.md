---
UID: NF:d3dkmthk.D3DKMTSubmitCommandToHwQueue
title: D3DKMTSubmitCommandToHwQueue function (d3dkmthk.h)
description: Used to submit a command to the hardware queue.
old-location: display\d3dkmtsubmitcommandtohwqueue.htm
ms.date: 03/02/2022
keywords: ["D3DKMTSubmitCommandToHwQueue function"]
ms.keywords: D3DKMTSubmitCommandToHwQueue, D3DKMTSubmitCommandToHwQueue function [Display Devices], d3dkmthk/D3DKMTSubmitCommandToHwQueue, display.d3dkmtsubmitcommandtohwqueue
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
 - D3DKMTSubmitCommandToHwQueue
 - d3dkmthk/D3DKMTSubmitCommandToHwQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTSubmitCommandToHwQueue
---

# D3DKMTSubmitCommandToHwQueue function

## -description

Used to submit a command to the hardware queue.

## -parameters

### -param unnamedParam1 [in]

A [D3DKMT_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md) structure holding the information needed to submit a command to the hardware queue.

## -returns

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The device context was called successfully. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md)
