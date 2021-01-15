---
UID: NS:d3dkmthk._D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
title: _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE (d3dkmthk.h)
description: A structure that contains information to submit a wait on the hardware queue.
old-location: display\d3dkmt_submitwaitforsyncobjectstohwqueue_.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure"]
ms.keywords: D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE , D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, d3dkmthk/D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, display.d3dkmt_submitwaitforsyncobjectstohwqueue_
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
req.typenames: D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
f1_keywords:
 - _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
 - d3dkmthk/_D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
 - D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
 - d3dkmthk/D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
 - D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
---

# _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure


## -description

A structure that contains information to submit a wait on the hardware queue.

## -struct-fields

### -field hHwQueue

Context queue to submit the command to.

### -field ObjectCount

Number of objects to wait on.

### -field ObjectHandleArray

Handles to monitored fence synchronization objects to wait on.

### -field FenceValueArray

Monitored fence values to be waited.

