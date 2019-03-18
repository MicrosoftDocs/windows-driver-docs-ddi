---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
title: D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
author: windows-driver-content
description: Used to output duplicate handle to a hardware queue.
tech.root: display
ms.assetid: b6e8eaac-5ded-4ff8-816d-c1efe6750293
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
ms.keywords: D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE, D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmthk.h
api_name: 
 - D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
product:
- Windows
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6
---

# D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE structure

## -description

Used to output duplicate handle to a hardware queue.

## -struct-fields

### -field hSource

A handle to the source allocation to present from.

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field BroadcastHwQueueCount

Specifies the number of hardware queues to broadcast this signal to.

### -field hHwQueues

A handle to an array of hardware queues.

### -field PresentRegions

Dirty and move regions.

### -field Flags

Flags from the D3DKMT_OUTPUTDUPLPRESENTFLAGS enumeration that specify output behavior.

### -field hIndirectHwQueue
 
A handle to the indirect hardware queue.

## -remarks

## -see-also