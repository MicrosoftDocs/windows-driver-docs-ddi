---
UID: NS:d3dumddi._D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
title: _D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE (d3dumddi.h)
description: A structure that contains information to present Blt to the hardware queue.
ms.date: 10/19/2018
keywords: ["D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE structure"]
ms.keywords: _D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE, D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE,
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
 - d3dumddi/_D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
 - D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
 - d3dumddi/D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
 - D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE
product:
 - Windows
---

# _D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE structure


## -description

A structure that contains information to present Blt to the hardware queue.

## -struct-fields

### -field hSrcAllocation

[in] The allocation of which content will be presented.

### -field hDstAllocation

[in] The destination allocation of the present, if non-zero.

### -field hHwQueue

[in] Hardware queue being submitted to.

### -field HwQueueProgressFenceId

Hardware queue progress fence ID that will be signaled when the Present Blt is done on the GPU.

### -field PrivateDriverDataSize

The size of pPrivateDriverData.

### -field pPrivateDriverData

Private driver data to pass to [Present](nc-d3dumddi-pfnd3dddi_present.md).

