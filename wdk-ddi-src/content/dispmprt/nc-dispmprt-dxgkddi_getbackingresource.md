---
UID: NC:dispmprt.DXGKDDI_GETBACKINGRESOURCE
title: DXGKDDI_GETBACKINGRESOURCE (dispmprt.h)
description: Gets any physical backings for the virtual device MMIO BARs.
ms.assetid: b74c4429-875a-4495-bd9f-ee3d6bfd69d7
ms.date: 10/19/2018
keywords: ["DXGKDDI_GETBACKINGRESOURCE callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_GETBACKINGRESOURCE"
 - "DXGKDDI_GETBACKINGRESOURCE"
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
- DXGKDDI_GETBACKINGRESOURCE
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# DXGKDDI_GETBACKINGRESOURCE callback function

## -description

Gets any physical backings for the virtual device MMIO (memory mapped input output) BARs (base address registers).

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

## -parameters

### -param Context

A handle to the device context.

### -param pArgs

Pointer to a [DXGKARG_GETBACKINGRESOURCE](ns-dispmprt-_dxgkarg_getbackingresource.md) structure.

## -returns

Returns:

* STATUS_SUCCESS The IHV system did not encounter any errors.
* STATUS_INVALID_DEVICE_REQUEST The virtual device encountered an error and should be forcibly stopped. Failure here will cause virtual device failure.

## -remarks


## -see-also
