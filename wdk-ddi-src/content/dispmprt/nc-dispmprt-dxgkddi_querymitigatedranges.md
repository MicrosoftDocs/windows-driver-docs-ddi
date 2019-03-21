---
UID: NC:dispmprt.DXGKDDI_QUERYMITIGATEDRANGES
title: DXGKDDI_QUERYMITIGATEDRANGES
author: windows-driver-content
description: This function is called from the virtual PCI system to the kernel mode driver to get the list of pages in the virtual function’s BARs that need to be mitigated.
tech.root: display
ms.assetid: 80e889c4-cf80-4556-b3c8-643cdf21995e
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
req.header: dispmprt.h
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_QUERYMITIGATEDRANGES
product: 
 - Windows
targetos: Windows
---

# DXGKDDI_QUERYMITIGATEDRANGES callback function

## -description

This function is called from the virtual PCI system to the kernel mode driver to get the list of pages in the virtual function’s BARs that need to be mitigated.

## -prototype

```
//Declaration

DXGKDDI_QUERYMITIGATEDRANGES DxgkddiQuerymitigatedranges; 

// Definition

NTSTATUS DxgkddiQuerymitigatedranges 
(
	HANDLE Context
	DXGKARG_QUERYMITIGATEDRANGES * pArgs
)
{...}

```

## -parameters

### -param Context

The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

Pointer to the DXGKARG_QUERYMITIGATEDRANGES structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks

This function returns the map of valid hardware pages to exclude from the virtual device exposed in the guest partition. Each base address register will be queried separately. These pages will never be exposed in the guest partition. Any operation on these pages by the guest VM will instead cause a trap into the user mode COM device driver.


## -see-also