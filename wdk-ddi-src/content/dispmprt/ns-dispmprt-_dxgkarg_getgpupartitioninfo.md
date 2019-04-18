---
UID: NS:dispmprt._DXGKARG_GETGPUPARTITIONINFO
title: _DXGKARG_GETGPUPARTITIONINFO
author: windows-driver-content
description: Arguments used to get physical GPU partition info.
tech.root: display
ms.assetid: 0ce6b0e0-5afe-4069-8839-dd1ea0611fe3
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_GETGPUPARTITIONINFO, DXGKARG_GETGPUPARTITIONINFO, *PDXGKARG_GETGPUPARTITIONINFO, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_GETGPUPARTITIONINFO, *PDXGKARG_GETGPUPARTITIONINFO
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_GETGPUPARTITIONINFO
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# _DXGKARG_GETGPUPARTITIONINFO structure

## -description

Arguments used to get physical GPU partition info.

## -struct-fields

### -field NumGpuPartitionOptions

On the input this is the size of the pGpuPartitionOptions output array. 
On the output this is the number of different ways the GPU could be partitioned. 
If the driver supports more options, it needs to return STATUS_BUFFER_TOO_SMALL and set NumGpuPartitionOptions to the number of supported options.

### -field pGpuPartitionOptions

Each element in the array, defines the number partitions the GPU can be divided into.
For example, GPIU could support 4 partitioning options: it could be divided to 2, 4, 8, 32 partitions.

### -field CurrentGpuPartitionCount
 
The number of partitions, the GPU is currently is configured to support.

## -remarks

## -see-also
