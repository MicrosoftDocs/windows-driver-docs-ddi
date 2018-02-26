---
UID: NS:d3dkmthk._D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
title: "_D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE"
author: windows-driver-content
description: A structure holding information to submit a signal to the hardware queue.
old-location: display\d3dkmt_submitsignalsyncobjectstohwqueue.htm
old-project: display
ms.assetid: BD192367-4960-4FD9-867F-02263AC93A61
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure [Display Devices], E, G, H, I, J, K, L, M, N, O, Q, S, T, U, W, Y, _, _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, d3dkmthk/D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, display.d3dkmt_submitsignalsyncobjectstohwqueue"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
---

# _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure


## -description


A structure holding information to submit a signal to the hardware queue.


## -syntax


````
typedef struct _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE {
  D3DDDICB_SIGNALFLAGS Flags;
  ULONG                BroadcastHwQueueCount;
  const D3DKMT_HANDLE  *BroadcastHwQueueArray;
  UINT                 ObjectCount;
  const D3DKMT_HANDLE  *ObjectHandleArray;
  const UINT64         *FenceValueArray;
} D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE;
````


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


