---
UID: NC:dispmprt.DXGKDDI_QUERYMITIGATEDRANGECOUNT
title: DXGKDDI_QUERYMITIGATEDRANGECOUNT
author: windows-driver-content
description: This function is called to get the count of the number of ranges per BAR that need to be mitigated.
tech.root: display
ms.assetid: a8e1860b-026a-4de4-8219-e3e40cfbc837
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
 - DXGKDDI_QUERYMITIGATEDRANGECOUNT
product: 
 - Windows
targetos: Windows
---

# DXGKDDI_QUERYMITIGATEDRANGECOUNT callback function

## -description

This function is called to get the count of the number of ranges per BAR that need to be mitigated (trapped and re-redirected to the user mode emulation DLL).

## -prototype

```
//Declaration

DXGKDDI_QUERYMITIGATEDRANGECOUNT DxgkddiQuerymitigatedrangecount; 

// Definition

VOID DxgkddiQuerymitigatedrangecount 
(
	HANDLE Context
	DXGKARG_QUERYMITIGATEDRANGECOUNT * pArgs
)
{...}

```

## -parameters

### -param Context

The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

A pointer to the DXGKARG_QUERYMITIGATEDRANGECOUNT structure.

## -returns

Returns VOID.

## -remarks


## -see-also