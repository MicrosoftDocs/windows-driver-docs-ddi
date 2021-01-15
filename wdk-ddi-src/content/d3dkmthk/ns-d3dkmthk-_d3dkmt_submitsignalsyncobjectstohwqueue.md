---
UID: NS:d3dkmthk._D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
title: _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE (d3dkmthk.h)
description: A structure holding information to submit a signal to the hardware queue.
old-location: display\d3dkmt_submitsignalsyncobjectstohwqueue.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure"]
ms.keywords: D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, d3dkmthk/D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, display.d3dkmt_submitsignalsyncobjectstohwqueue
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
f1_keywords:
 - _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
 - d3dkmthk/_D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
 - D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
 - d3dkmthk/D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
 - D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
---

# _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure


## -description

A structure holding information to submit a signal to the hardware queue.

## -struct-fields

### -field Flags

Flags that specify signal behavior.

### -field BroadcastHwQueueCount

Specifies the number of hardware queues to broadcast this signal to.

### -field BroadcastHwQueueArray

Specifies hardware queue handles to broadcast to.

### -field ObjectCount

Number of objects to signal.

### -field ObjectHandleArray

Handles to monitored fence synchronization objects to signal.

### -field FenceValueArray

Monitored fence values to signal.

