---
UID: NS:d3d12umddi.D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2
title: D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: Signals a synchronization object.
tech.root: display
ms.assetid: 45bbd40e-92a8-4ceb-a220-b196a383ba70
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2, D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2, 
req.header: d3d12umddi.h
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
req.typenames: D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2
product: 
 - Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021
---

# D3D12DDICB_SIGNALSYNCHRONIZATIONOBJECT2 structure

## -description

Signals a synchronization object.

## -struct-fields

### -field hContext

[in] Specify the context that should signal the objects.

### -field ObjectCount

[in] Number of object to signal.

### -field ObjectHandleArray

[in] A handle to an array of synchronization objects to signal.

### -field Flags

[in] Specify signal behavior.

### -field BroadcastContextCount

[in] Specifies the number of context to broadcast this signal buffer to.

### -field BroadcastContext

[in] A handle an array of context to broadcast to.

### -field FenceValue

[in] Fence value to be signaled.

### -field CpuEventHandle
 
[in] Handle of a CPU event to be signaled.

## -remarks

## -see-also