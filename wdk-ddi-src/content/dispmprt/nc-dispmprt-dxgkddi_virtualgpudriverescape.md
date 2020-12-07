---
UID: NC:dispmprt.DXGKDDI_VIRTUALGPUDRIVERESCAPE
title: DXGKDDI_VIRTUALGPUDRIVERESCAPE
description: This function passes information between a user mode emulation DLL and the kernel mode driver.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKDDI_VIRTUALGPUDRIVERESCAPE callback function"]
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
 - DXGKDDI_VIRTUALGPUDRIVERESCAPE
 - dispmprt/DXGKDDI_VIRTUALGPUDRIVERESCAPE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_VIRTUALGPUDRIVERESCAPE
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_VIRTUALGPUDRIVERESCAPE callback function


## -description

This function passes information between a user mode emulation DLL and the kernel mode driver. This function is called in response to IOCTL_GPUP_DRIVER_ESCAPE.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_GPU_PARTITION_INTERFACE](ns-dispmprt-_dxgkddi_gpu_partition_interface.md) structure.

### -param pArgs

[in, out] A pointer to a DXGK_VIRTUALGPUDRIVERESCAPE structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_VIRTUALGPUDRIVERESCAPE DxgkddiVirtualgpudriverescape; 

// Definition

NTSTATUS DxgkddiVirtualgpudriverescape 
(
	HANDLE Context
	PDXGK_VIRTUALGPUDRIVERESCAPE pArgs
)
{...}

```

## -remarks

## -see-also

