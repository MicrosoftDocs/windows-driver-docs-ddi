---
UID: NC:dispmprt.DXGKDDI_GETMMIORANGECOUNT
title: DXGKDDI_GETMMIORANGECOUNT
author: windows-driver-content
description: Gets the number of memory ranges in the virtual device's MMIO (memory mapped input output) BARs.
ms.assetid: 3af0d571-a797-477a-a725-6b88ef045d73
ms.date: 10/19/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	dispmprt.h
api_name: 
-	DXGKDDI_GETMMIORANGECOUNT
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_GETMMIORANGECOUNT callback function

## -description

Gets the number of memory ranges in the virtual device's MMIO (memory mapped input output) BARs (base address registers).

## -prototype

```cpp
//Declaration

DXGKDDI_GETMMIORANGECOUNT DxgkddiGetmmiorangecount; 

// Definition

NTSTATUS DxgkddiGetmmiorangecount 
(
	HANDLE Context
	DXGKARG_GETMMIORANGECOUNT * pArgs
)
{...}

```

## -parameters

### -param Context

A handle to the device context.

### -param pArgs

Pointer to a [DXGKARG_GETMMIORANGECOUNT](ns-dispmprt-_dxgkarg_getmmiorangecount.md) structure.

## -returns

Returns:

* STATUS_SUCCESS The IHV system did not encounter any errors.
* STATUS_INVALID_DEVICE_REQUEST The virtual device encountered an error and should be forcibly stopped. Failure here will cause virtual device failure.

## -remarks

This function will get the total count of memory rages that make up each of the virtual device BARs. Each range represent a group of pages that is either directly mapped from one of the physical device BARs, intercepted by the software virtual device (but still backed by physical device memory), or completely virtual and not mapped.  

Note that if a device is fully virtual, and does not require any intercepts or virtual pages, this function can be unimplemented and NULL in the interface.

## -see-also
