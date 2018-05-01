---
UID: NS:d3dumddi._D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
title: "_D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE"
author: windows-driver-content
description: A structure that holds information to submit a signal synchronization object to a hardware queue.
old-location: display\d3dddicb_submitsignalsyncobjectstohwqueue.htm
old-project: display
ms.assetid: 22AA35D4-D287-443B-A49D-87C20BD436AA
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, d3dumddi/D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, display.d3dddicb_submitsignalsyncobjectstohwqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
---

# _D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure


## -description


A structure that holds information to submit a signal synchronization object to a hardware queue.


## -struct-fields




### -field Flags

Specifies signal behavior.


### -field BroadcastHwQueueCount

Specifies the number of hardware queues to broadcast this signal to.


### -field BroadcastHwQueueArray

Specifies hardware queue handles to broadcast to.



### -field ObjectCount

Number of objects to signal.



### -field ObjectHandleArray

Handles to monitored fence synchronization objects to signal.


### -field FenceValueArray

monitored fence values to signal.


