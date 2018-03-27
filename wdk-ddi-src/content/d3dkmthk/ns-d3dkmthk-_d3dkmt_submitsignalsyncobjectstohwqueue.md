---
UID: NS:d3dkmthk._D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
title: "_D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE"
author: windows-driver-content
description: A structure holding information to submit a signal to the hardware queue.
old-location: display\d3dkmt_submitsignalsyncobjectstohwqueue.htm
old-project: display
ms.assetid: BD192367-4960-4FD9-867F-02263AC93A61
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, d3dkmthk/D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, display.d3dkmt_submitsignalsyncobjectstohwqueue
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
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


