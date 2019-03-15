---
UID: NS:d3dumddi._D3DDDICB_SUBMITPRESENTTOHWQUEUE
title: _D3DDDICB_SUBMITPRESENTTOHWQUEUE (d3dumddi.h)
description: Arguments used by the PFND3DDDI_SUBMITPRESENTTOHWQUEUECB callback function.
ms.assetid: 47ca9041-9e7a-4afa-9e82-0148f8985078
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DDDICB_SUBMITPRESENTTOHWQUEUE, D3DDDICB_SUBMITPRESENTTOHWQUEUE, 
req.header: d3dumddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DDDICB_SUBMITPRESENTTOHWQUEUE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dumddi.h
api_name: 
- _D3DDDICB_SUBMITPRESENTTOHWQUEUE
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# _D3DDDICB_SUBMITPRESENTTOHWQUEUE structure

## -description

Arguments used by the [PFND3DDDI_SUBMITPRESENTTOHWQUEUECB](nc-d3dumddi-pfnd3dddi_submitpresenttohwqueuecb.md) callback function.

## -struct-fields

### -field BroadcastSrcAllocations

Allocations for which content will be presented.

### -field BroadcastDstAllocations

If non-zero, represents the destination allocations of the present.

### -field hHwQueues

An array of hardware queues being submitted to.

### -field BroadcastHwQueueCount

The number of broadcast hardware queues.

### -field PrivateDriverDataSize

The total size in bytes of the private data buffer.

### -field pPrivateDriverData
 
Pointer to the private data to pass to DdiPresent.

## -remarks

## -see-also
