---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
title: _D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
author: windows-driver-content
description: Used by the D3DKMTOutputDuplPresentToHwQueue function to output the duplicate handle of a hardware queue.
tech.root: display
ms.assetid: f970fcdd-e98a-4ad5-9536-7b08bbd19645
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE"
 - "_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE, D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE, 
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
 - _D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# _D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE structure

## -description

Used by the [D3DKMTOutputDuplPresentToHwQueue](nf-d3dkmthk-d3dkmtoutputduplpresenttohwqueue.md) function to output the duplicate handle of a hardware queue.

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

Dirty and move regions, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present_rgns">D3DKMT_PRESENT_RGNS</a>.

### -field Flags

Flags from the D3DKMT_OUTPUTDUPLPRESENTFLAGS enumeration that specify output behavior.

### -field hIndirectHwQueue

A handle to the indirect hardware queue.

## -remarks

## -see-also
