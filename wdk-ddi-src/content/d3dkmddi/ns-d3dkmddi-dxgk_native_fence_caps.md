---
UID: NS:d3dkmddi._DXGK_NATIVE_FENCE_CAPS
tech.root: display
title: DXGK_NATIVE_FENCE_CAPS
ms.date: 11/08/2024
targetos: Windows
description: Learn more about the DXGK_NATIVE_FENCE_CAPS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_NATIVE_FENCE_CAPS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_NATIVE_FENCE_CAPS
 - DXGK_NATIVE_FENCE_CAPS
f1_keywords:
 - _DXGK_NATIVE_FENCE_CAPS
 - d3dkmddi/_DXGK_NATIVE_FENCE_CAPS
 - DXGK_NATIVE_FENCE_CAPS
 - d3dkmddi/DXGK_NATIVE_FENCE_CAPS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NATIVE_FENCE_CAPS
---

## -description

A kernel-mode display miniport driver (KMD) returns the GPU's native fence capabilities in **DXGK_NATIVE_FENCE_CAPS** when its [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function is called with the [**DXGKQAITYPE_NATIVE_FENCE_CAPS**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) query adapter info type.

## -struct-fields

### -field MonitoredValueStride

To save memory, the OS packs non-shareable native GPU fence objects together into the same memory page. **MonitoredValueStride** specifies the stride in bytes between OS-managed storage for different fence objects sharing the same memory page.

### -field MapToGpuSystemProcess

Specifies whether native fence current and monitored values should be mapped to a GPU system process address space for use by the context management processor.

### -field MinimumAddress

Minimum virtual address for GPU VA mappings (optional).

### -field MaximumAddress

Maximum virtual address for GPU VA mappings (optional).

### -field Reserved[28]

Reserved for system use.

## -remarks

The **CurrentValueStride** and **MonitoredValueStride** values specify the stride in bytes between OS-managed storage for different fence objects sharing the same memory page.

When the driver sets **MapToGpuSystemProcess**, it's instructing the OS to reserve a system process GPU virtual address space for the context management processor to use, and to create GPU VA mappings into that address space for native fence **CurrentValue** and **MonitoredValue**. These GPU VAs are subsequently passed to the KMD fence creation callback as [**DXGKARG_CREATENATIVEFENCE's**](ns-d3dkmddi-dxgkarg_createnativefence.md) **CurrentValueSystemProcessGpuVa** and **MonitoredValueSystemProcessGpuVa**.

The KMD can also specify an optional **MinimumAddress** and **MaximumAddress** to restrict native fence GPU VA mappings within a chosen range for both process address space and system address space. This limit will apply to all native fences created on the system.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DXGKQAITYPE_NATIVE_FENCE_CAPS**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)
