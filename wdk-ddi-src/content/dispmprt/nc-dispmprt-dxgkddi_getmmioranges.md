---
UID: NC:dispmprt.DXGKDDI_GETMMIORANGES
title: DXGKDDI_GETMMIORANGES (dispmprt.h)
description: Get the memory ranges for a single MMIO (memory mapped input output) BAR in the virtual device.
ms.assetid: b5bdfe10-a053-4003-94e9-0205e49f05c6
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "dispmprt/DXGKDDI_GETMMIORANGES"
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
- apiref
api_type: 
- UserDefined
api_location: 
- dispmprt.h
api_name: 
- DXGKDDI_GETMMIORANGES
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_GETMMIORANGES callback function

## -description

Get the memory ranges for a single MMIO (memory mapped input output) BAR (base address register) in the virtual device.

## -prototype

```cpp
//Declaration

DXGKDDI_GETMMIORANGES DxgkddiGetmmioranges; 

// Definition

NTSTATUS DxgkddiGetmmioranges 
(
	HANDLE Context
	PDXGKARG_GETMMIORANGES pArgs
)
{...}

```

## -parameters

### -param Context

A handle to the device context.

### -param pArgs

Pointer to a [DXGKARG_GETMMIORANGES](ns-dispmprt-_dxgkarg_getmmioranges.md) structure.

## -returns

Returns:

* STATUS_SUCCESS The IHV system did not encounter any errors.
* STATUS_INVALID_DEVICE_REQUEST The virtual device encountered an error and should be forcibly stopped. Failure here will cause virtual device failure.
* BUFFER_TO_SMALL may result in this being called again with a larger buffer.

## -remarks

This callback function gets the specific ranges on which intercepts and mapping must be placed. This is a more flexible scatter/gather mapping of the BARs than the general SR-IOV (single-root input/output virtualization) solution that allows for VF (virtual function) BARS (base address registers) to be different sized than the physical bars and map/emulate any order of pages from any physical bar to any virtual bar. This function MUST contain a mapping for every page in the virtual bar. If it does not the device will fail to be created.

## -see-also
