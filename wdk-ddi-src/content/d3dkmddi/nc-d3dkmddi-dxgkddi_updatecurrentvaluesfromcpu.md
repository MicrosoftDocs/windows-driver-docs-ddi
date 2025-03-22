---
UID: NC:d3dkmddi.DXGKDDI_UPDATECURRENTVALUESFROMCPU
tech.root: display
title: DXGKDDI_UPDATECURRENTVALUESFROMCPU
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_UPDATECURRENTVALUESFROMCPU function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_UPDATECURRENTVALUESFROMCPU
f1_keywords:
 - DXGKDDI_UPDATECURRENTVALUESFROMCPU
 - d3dkmddi/DXGKDDI_UPDATECURRENTVALUESFROMCPU
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_UPDATECURRENTVALUESFROMCPU
---

# DXGKDDI_UPDATECURRENTVALUESFROMCPU function (d3dkmddi.h)

## -description

The OS calls **DxgkDdiUpdateCurrentValuesFromCpu** to update the **CurrentValue** of a batch of native fences from the CPU.

## -parameters

### -param pUpdateCurrentValuesFromCpu

[in] Pointer to a [**DXGKARG_UPDATECURRENTVALUESFROMCPU**](ns-d3dkmddi-dxgkarg_updatecurrentvaluesfromcpu.md) structure that contains the current values to update.

## -returns

## -remarks

 This DDI is used to support the existing "signal fence from CPU" API semantics. Instead of *Dxgkrnl* writing a new **CurrentValue**, the driver is asked to write to **CurrentValue** in order to give drivers an opportunity to insert any required pre-write synchronization/barriers. The OS synchronizes CPU-side updates and guarantees that the most up to date value is available to **DxgkDdiUpdateCurrentValuesFromCpu**. After updating **CurrentValue**, the driver must trigger the GPU to unblock hardware queues that were waiting on this fence and got unblocked with the update to **CurrentValue**.

In a nutshell the steps to be followed by the driver are:

``` pseudocode

for i = 1 : NumFences
  1. Insert pre-write memory barrier if required
  2. write new value to CurrentValueCpuVa
  3. trigger GPU to unblock any HwQueues that got unblocked by the updated CurrentValue
end
```

The OS only guarantees that the **CurrentValueKernelCpuVa** pointer is valid for the duration of this DDI call, and not before or after it. Hence, KMD must never cache this pointer for use elsewhere.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_UPDATECURRENTVALUESFROMCPU**](ns-d3dkmddi-dxgkarg_updatecurrentvaluesfromcpu.md)
