---
UID: NC:dispmprt.DXGKDDI_GETBACKINGRESOURCE
title: DXGKDDI_GETBACKINGRESOURCE (dispmprt.h)
description: Gets any physical backings for the virtual device MMIO BARs.
ms.date: 10/19/2018
keywords: ["DXGKDDI_GETBACKINGRESOURCE callback function"]
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_GETBACKINGRESOURCE
 - dispmprt/DXGKDDI_GETBACKINGRESOURCE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_GETBACKINGRESOURCE
dev_langs:
 - c++
---

# DXGKDDI_GETBACKINGRESOURCE callback function


## -description

Gets any physical backings for the virtual device MMIO (memory mapped input output) BARs (base address registers).

## -parameters

### -param Context

A handle to the device context.

### -param pArgs

Pointer to a [DXGKARG_GETBACKINGRESOURCE](ns-dispmprt-_dxgkarg_getbackingresource.md) structure.

## -returns

Returns:

* STATUS_SUCCESS The IHV system did not encounter any errors.
* STATUS_INVALID_DEVICE_REQUEST The virtual device encountered an error and should be forcibly stopped. Failure here will cause virtual device failure.

## -prototype

```cpp
//Declaration

DXGKDDI_GETBACKINGRESOURCE DxgkddiGetbackingresource; 

// Definition

NTSTATUS DxgkddiGetbackingresource 
(
	HANDLE Context
	DXGKARG_GETBACKINGRESOURCE * pArgs
)
{...}

```

## -remarks

## -see-also

