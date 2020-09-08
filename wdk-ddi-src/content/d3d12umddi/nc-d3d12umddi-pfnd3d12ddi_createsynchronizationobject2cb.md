---
UID: NC:d3d12umddi.PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB
title: PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 2.6 and later user-mode display drivers.
tech.root: display
ms.assetid: fa9dd71f-6178-4fe3-9519-dfca15f76c81
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB callback function"]
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
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021, 19H1
f1_keywords:
 - PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB
 - d3d12umddi/PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB callback function


## -description

Creates a GPU synchronization object that a device context can signal and wait for. Used by WDDM 2.6 and later user-mode display drivers.

## -parameters

### -param hDevice

A handle to the display device (that is, the graphics context) that will own the synchronization object that pfnCreateSynchronizationObject2Cb creates.

### -param Arg2

A pointer to a D3D12DDICB_CREATESYNCHRONIZATIONOBJECT2 structure that describes the synchronization object to create.

## -returns

Returns one of the following HRESULT values:

|Return code|Description|
|---|---|
|S_OK|The synchronization object was successfully created.|
|E_OUTOFMEMORY|The function could not allocate memory that was required for it to complete.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

This function might also return other HRESULT values.

## -prototype

```
//Declaration

PFND3D12DDI_CREATESYNCHRONIZATIONOBJECT2CB Pfnd3d12ddiCreatesynchronizationobject2cb; 

// Definition

HRESULT Pfnd3d12ddiCreatesynchronizationobject2cb 
(
	D3D12DDI_HRTDEVICE hDevice
	D3D12DDICB_CREATESYNCHRONIZATIONOBJECT2 *
)
{...}

```

## -remarks

## -see-also

