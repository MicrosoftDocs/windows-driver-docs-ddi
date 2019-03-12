---
UID: NS:d3dkmddi._DXGK_GPUPCAPS
title: DXGK_GPUPCAPS
author: windows-driver-content
description: The GPU capabilities for a kernel mode display driver.
tech.root: display
ms.assetid: 2cdb8141-80cb-455e-8e15-af606df0c28f
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
ms.keywords: DXGK_GPUPCAPS, DXGK_GPUPCAPS, 
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGK_GPUPCAPS
product:
- Windows
targetos: Windows
---

# DXGK_GPUPCAPS structure

## -description

The GPU capabilities for a kernel mode display driver.

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