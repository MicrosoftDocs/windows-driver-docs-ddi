---
UID: NS:d3dkmthk._D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
title: _D3DKMT_SUBMITPRESENTBLTTOHWQUEUE (d3dkmthk.h)
description: Contains arguments needed for the D3DKMTSubmitPresentBltToHwQueue function.
ms.date: 10/19/2018
keywords: ["D3DKMT_SUBMITPRESENTBLTTOHWQUEUE structure"]
ms.keywords: _D3DKMT_SUBMITPRESENTBLTTOHWQUEUE, D3DKMT_SUBMITPRESENTBLTTOHWQUEUE,
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
 - d3dkmthk/_D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
 - D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
 - d3dkmthk/D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
 - D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
product:
 - Windows
---

# _D3DKMT_SUBMITPRESENTBLTTOHWQUEUE structure


## -description

Contains arguments needed for the [D3DKMTSubmitPresentBltToHwQueue](nf-d3dkmthk-d3dkmtsubmitpresentblttohwqueue.md) function.

## -struct-fields

### -field hHwQueue

Handle to the created queue.

### -field HwQueueProgressFenceId

Handle to the hardware queue progress fence id.

### -field PrivatePresentData

The private present data.

