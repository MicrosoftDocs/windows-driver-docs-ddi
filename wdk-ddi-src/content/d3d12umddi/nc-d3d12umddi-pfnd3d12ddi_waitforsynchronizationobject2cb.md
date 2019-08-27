---
UID: NC:d3d12umddi.PFND3D12DDI_WAITFORSYNCHRONIZATIONOBJECT2CB
title: PFND3D12DDI_WAITFORSYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Inserts a wait for the specified synchronization objects in the specified context stream.
tech.root: display
ms.assetid: 772903a7-9395-46d7-b6ca-6d6086e13672
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_WAITFORSYNCHRONIZATIONOBJECT2CB"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_WAITFORSYNCHRONIZATIONOBJECT2CB
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021, 19H1
---

# PFND3D12DDI_WAITFORSYNCHRONIZATIONOBJECT2CB callback function

## -description

Inserts a wait for the specified synchronization objects in the specified context stream.

## -prototype

```
//Declaration

PFND3D12DDI_WAITFORSYNCHRONIZATIONOBJECT2CB Pfnd3d12ddiWaitforsynchronizationobject2cb; 

// Definition

HRESULT Pfnd3d12ddiWaitforsynchronizationobject2cb 
(
	D3D12DDI_HRTDEVICE hDevice
	 const D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2 *
)
{...}

```

## -parameters

### -param hDevice

Handle to a device.

### -param *

Pointer to a [D3D12DDICB_WAITFORSYNCHRONIZATIONOBJECT2](ns-d3d12umddi-d3d12ddicb_waitforsynchronizationobject2.md) structure.

## -returns

Returns HRESULT.

## -remarks



## -see-also
