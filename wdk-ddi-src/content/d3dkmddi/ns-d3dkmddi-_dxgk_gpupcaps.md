---
UID: NS:d3dkmddi._DXGK_GPUPCAPS
title: DXGK_GPUPCAPS
description: Learn more about the DXGK_GPUPCAPS structure.
tech.root: display
ms.date: 10/04/2024
keywords: ["DXGK_GPUPCAPS structure"]
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
---

# DXGK_GPUPCAPS structure

## -description

A kernel-mode display driver uses the **DXGK_GPUPCAPS** structure to identify its GPU partitioning (GPU-P) capabilities.

## -struct-fields

### -field Caps

Union containing the capability flags for the GPU-P device.

### -field Caps.VirtualMachineHibernation

The driver sets this bit if it supports guest hibernation for GPU-P devices. The support for guest hibernation is optional and not required for driver certification. A VM that has hibernation enabled and a GPU-P adapter added will fail to start if the driver doesn't support guest hibernation.

### -field Caps.HotDriverUpdate

The driver sets this bit if it supports hot driver updates for GPU-P devices.

### -field Caps.LiveMigration

The driver sets this bit if it supports [live migration for GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices). Added in Windows 11, version 24H2 (WDDM 3.2).

### -field Caps.ScatterMapReserve

The driver sets this bit if it supports *DxgkDdiSetVirtualGpuResources2, which will be added in a future release. Added in Windows 11, version 24H2 (WDDM 3.2).

### -field Caps.Reserved

Reserved.

### -field Caps.Value

The UINT value that represents the combined bitfields of the GPU-P capabilities.

## -remarks

The KMD must fill out these caps in response to a [**DXGKQAITYPE_GPUPCAPS**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) request. The OS queries for these during device initialization after it calls [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) and only if the adapter supports GPU partitioning.

## -see-also

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)
