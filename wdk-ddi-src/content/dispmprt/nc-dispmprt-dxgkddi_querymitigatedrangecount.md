---
UID: NC:dispmprt.DXGKDDI_QUERYMITIGATEDRANGECOUNT
title: DXGKDDI_QUERYMITIGATEDRANGECOUNT
description: This function is called to get the count of the number of ranges per BAR that need to be mitigated.
tech.root: display
ms.assetid: a8e1860b-026a-4de4-8219-e3e40cfbc837
ms.date: 04/04/2019
keywords: ["DXGKDDI_QUERYMITIGATEDRANGECOUNT callback function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_QUERYMITIGATEDRANGECOUNT
 - dispmprt/DXGKDDI_QUERYMITIGATEDRANGECOUNT
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
dev_langs:
 - c++
---

# DXGKDDI_QUERYMITIGATEDRANGECOUNT callback function


## -description

This function is called to get the count of the number of ranges per BAR that need to be mitigated (trapped and re-redirected to the user mode emulation DLL).

## -parameters

### -param Context

The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

A pointer to the DXGKARG_QUERYMITIGATEDRANGECOUNT structure.

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

## -remarks

## -see-also

