---
UID: NS:d3dkmthk._D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
title: _D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
author: windows-driver-content
description:
ms.assetid: 2454c446-7a3a-49f5-918f-d5e26d043e99
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	_D3DKMT_SUBMITPRESENTBLTTOHWQUEUE
product: 
- Windows
targetos: Windows
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

