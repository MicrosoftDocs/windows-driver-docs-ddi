---
UID: NS:dispmprt._DXGKDDI_GPU_PARTITION_INTERFACE
title: _DXGKDDI_GPU_PARTITION_INTERFACE
description: Used to query how a GPU can be partitioned for use in Virtual Machines and create or destroy a virtual GPU.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKDDI_GPU_PARTITION_INTERFACE structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKDDI_GPU_PARTITION_INTERFACE, DXGKDDI_GPU_PARTITION_INTERFACE, *PDXGKDDI_GPU_PARTITION_INTERFACE,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKDDI_GPU_PARTITION_INTERFACE, *PDXGKDDI_GPU_PARTITION_INTERFACE
targetos: Windows
ms.custom: rs6, 19H1
f1_keywords:
 - _DXGKDDI_GPU_PARTITION_INTERFACE
 - dispmprt/_DXGKDDI_GPU_PARTITION_INTERFACE
 - PDXGKDDI_GPU_PARTITION_INTERFACE
 - dispmprt/PDXGKDDI_GPU_PARTITION_INTERFACE
 - DXGKDDI_GPU_PARTITION_INTERFACE
 - dispmprt/DXGKDDI_GPU_PARTITION_INTERFACE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKDDI_GPU_PARTITION_INTERFACE
 - PDXGKDDI_GPU_PARTITION_INTERFACE
 - DXGKDDI_GPU_PARTITION_INTERFACE
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKDDI_GPU_PARTITION_INTERFACE structure


## -description

Used to query how a GPU can be partitioned for use in Virtual Machines and create or destroy a virtual GPU.

A miniport driver must support all functions in this group.

## -struct-fields

### -field Size

[in] Size of a virtual GPU.

### -field Version

[in] Version.

### -field Context

[out] The context.

### -field InterfaceReference

[out]

### -field InterfaceDereference

[out]

### -field DxgkDdiGetGpuPartitionInfo

[out]

### -field DxgkDdiSetGpuPartitionCount

[out]

### -field DxgkDdiGetGpuEngines

[out]

### -field DxgkDdiGetVirtualGpuProfile

[out]

### -field DxgkDdiCreateVirtualGpu

[out]

### -field DxgkDdiGetVirtualGpuInfo

[out]

### -field DxgkDdiSetVirtualGpuResources

[out]

### -field DxgkDdiDestroyVirtualGpu

[out]

### -field DxgkDdiSuspendVirtualGpu

[out]

### -field DxgkDdiResumeVirtualGpu

[out]

### -field DxgkDdiVirtualGpuDriverEscape

[out]

### -field DxgkDdiSetVirtualGpuVmBus

[out]

## -remarks

## -see-also

