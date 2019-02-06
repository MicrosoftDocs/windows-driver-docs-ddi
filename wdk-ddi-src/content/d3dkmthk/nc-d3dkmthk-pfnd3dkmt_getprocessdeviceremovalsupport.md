---
UID: NC:d3dkmthk.PFND3DKMT_GETPROCESSDEVICEREMOVALSUPPORT
title: PFND3DKMT_GETPROCESSDEVICEREMOVALSUPPORT (d3dkmthk.h)
description: Implemented by the client driver to get process device removal support.
ms.assetid: a9c7b426-d67d-44d5-948d-017c0ee855cc
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
-	apiref
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	PFND3DKMT_GETPROCESSDEVICEREMOVALSUPPORT
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_GETPROCESSDEVICEREMOVALSUPPORT callback function

## -description

Implemented by the client driver to get process device removal support.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETPROCESSDEVICEREMOVALSUPPORT Pfnd3dkmtGetprocessdeviceremovalsupport;

// Definition

NTSTATUS Pfnd3dkmtGetprocessdeviceremovalsupport
(
	D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT *
)
{...}

PFND3DKMT_GETPROCESSDEVICEREMOVALSUPPORT


```

## -parameters

### -param D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT *

Pointer to a [D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT](ns-d3dkmthk-_d3dkmt_getprocessdeviceremovalsupport.md) structure that contains the information needed to get process device removal support.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_GETPROCESSDEVICEREMOVALSUPPORT](ns-d3dkmthk-_d3dkmt_getprocessdeviceremovalsupport.md) and then calling pfnd3dkmtGetProcessDeviceRemovalSupport.
