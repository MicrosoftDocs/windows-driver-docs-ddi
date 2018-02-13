---
UID: NS:d3dumddi._D3DDDICB_DESTROYHWQUEUE
title: "_D3DDDICB_DESTROYHWQUEUE"
author: windows-driver-content
description: A structure that holds information to destroy a hardware queue.
old-location: display\d3dddicb_destroyhwqueue.htm
old-project: display
ms.assetid: 80735E36-C483-4CD8-AB53-873BA5E997D0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDICB_DESTROYHWQUEUE, display.d3dddicb_destroyhwqueue, D3DDDICB_DESTROYHWQUEUE, _D3DDDICB_DESTROYHWQUEUE, D3DDDICB_DESTROYHWQUEUE structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_DESTROYHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYHWQUEUE
---

# _D3DDDICB_DESTROYHWQUEUE structure


## -description


A structure that holds information to destroy a hardware queue.


## -syntax


````
typedef struct _D3DDDICB_DESTROYHWQUEUE {
  HANDLE hHwQueue;
} D3DDDICB_DESTROYHWQUEUE;
````


## -struct-fields




### -field hHwQueue

Handle to the queue to destroy.

