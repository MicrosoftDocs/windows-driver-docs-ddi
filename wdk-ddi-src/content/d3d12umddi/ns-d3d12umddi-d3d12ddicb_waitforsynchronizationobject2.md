---
UID: NS:d3d12umddi.D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2
title: D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: Waits for synchronization object.
tech.root: display
ms.assetid: 61c6c871-5b24-4034-9540-9e20b2f668ce
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2, D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2, 
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
req.typenames: D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2
product: 
 - Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021, 19H1
---

# D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2 structure

## -description

Waits for synchronization object.

## -struct-fields

### -field hContext

[in] A handle to the context that should be waiting.

### -field ObjectCount

[in] The number of objects to wait on.

### -field ObjectHandleArray

[in] A handle to and array of synchronization objects to wait on.

### -field FenceValue
 
[in] Fence value to be waited.

## -remarks

## -see-also
