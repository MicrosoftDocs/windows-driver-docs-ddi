---
UID: NS:d3dkmddi._DXGK_GPUPCAPS
title: _DXGK_GPUPCAPS
description: The GPU capabilities for a kernel mode display driver.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGK_GPUPCAPS structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_GPUPCAPS, DXGK_GPUPCAPS,
req.header: d3dkmddi.h
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
req.typenames: DXGK_GPUPCAPS
targetos: Windows
ms.custom: rs6, 19H1
f1_keywords:
 - _DXGK_GPUPCAPS
 - d3dkmddi/_DXGK_GPUPCAPS
 - DXGK_GPUPCAPS
 - d3dkmddi/DXGK_GPUPCAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_GPUPCAPS
 - DXGK_GPUPCAPS
product:
 - Windows
---

# _DXGK_GPUPCAPS structure


## -description

The GPU capabilities for a kernel mode display driver.

These caps must be filled out by the KMD in response to **DXGKQAITYPE_GPUPCAPS** [QueryAdapterInfo](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) request. These are queried by the OS during device initialization after [DxgkDdiStartDevice](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) is called and only if the adapter supports GPU partitioning.

## -struct-fields

### -field Caps

### -field Caps.VirtualMachineHibernation

The driver sets the cap if guest hibernation is supported for GPU-P devices.

### -field Caps.HotDriverUpdate

The driver sets the cap if hot driver update is supported for GPU-P devices.

### -field Caps.Reserved

Reserved.

### -field Caps.Value

The driver sets the cap if VM save/restore is supported for GPU-P devices.

The support for guest hibernation is optional and not required for driver certification.

A VM, which has hibernation enabled and a GPU-P adapter added, will fail to start, if the driver does not support guest hibernation.

## -remarks

## -see-also

