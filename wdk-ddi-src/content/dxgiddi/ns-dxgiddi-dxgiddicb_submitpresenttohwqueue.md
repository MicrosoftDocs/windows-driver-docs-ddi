---
UID: NS:dxgiddi.DXGIDDICB_SUBMITPRESENTTOHWQUEUE
title: DXGIDDICB_SUBMITPRESENTTOHWQUEUE
author: windows-driver-content
description: Arguments used by the PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB callback function.
ms.assetid: 6a7a5e66-d569-44ef-8be6-a01ea4dbd3ab
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: DXGIDDICB_SUBMITPRESENTTOHWQUEUE, DXGIDDICB_SUBMITPRESENTTOHWQUEUE, 
req.header: dxgiddi.h
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
req.typenames: DXGIDDICB_SUBMITPRESENTTOHWQUEUE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dxgiddi.h
api_name: 
-	DXGIDDICB_SUBMITPRESENTTOHWQUEUE
product:
-	Windows
targetos: Windows
tech.root: display
---

# DXGIDDICB_SUBMITPRESENTTOHWQUEUE structure

## -description

Arguments used by the [PFNDDXGIDDI_SUBMITPRESENTTOHWQUEUECB](nc-dxgiddi-pfnddxgiddi_submitpresenttohwqueuecb.md) callback function.

## -struct-fields

### -field pDXGIContext
 
Pointer to a DXGI context.

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
