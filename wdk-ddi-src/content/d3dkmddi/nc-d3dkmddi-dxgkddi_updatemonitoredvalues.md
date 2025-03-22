---
UID: NC:d3dkmddi.DXGKDDI_UPDATEMONITOREDVALUES
tech.root: display
title: DXGKDDI_UPDATEMONITOREDVALUES
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_UPDATEMONITOREDVALUES function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PROFILE_LEVEL-1
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
 - DXGKDDI_UPDATEMONITOREDVALUES
f1_keywords:
 - DXGKDDI_UPDATEMONITOREDVALUES
 - d3dkmddi/DXGKDDI_UPDATEMONITOREDVALUES
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_UPDATEMONITOREDVALUES
---

# DXGKDDI_UPDATEMONITOREDVALUES function (d3dkmddi.h)

## -description

*Dxgkrnl* calls **DxgkDdiUpdateMonitoredValues** to instruct the kernel-mode display driver (KMD) to update a batch of monitored values.

## -parameters

### -param pUpdateMonitoredValues

[in] Pointer to a [**DXGKARG_UPDATEMONITOREDVALUES**](ns-d3dkmddi-dxgkarg_updatemonitoredvalues.md) structure that contains the monitored values to update.

## -returns

**DxgkDdiUpdateMonitoredValues** returns STATUS_SUCCESS if KMD was able to successfully update the batch of monitored values. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

**DxgkDdiUpdateMonitoredValues** executes at the device interrupt level and is thus synchronized with the monitored fence signaled interrupt service routine (ISR).

A KMD's **DxgkDdiUpdateMonitoredValues** implementation must guarantee that the [**CurrentValue**](/windows-hardware/drivers/display/native-gpu-fence-objects) read by any processor core after the call returns was written by the GPU context management processor after having observed the new [**MonitoredValue**](/windows-hardware/drivers/display/native-gpu-fence-objects).

**DxgkDdiUpdateMonitoredValues** is expected to write the **UpdatedValueArray** values to the location specified by **MonitoredValueGpuVa** while honoring the synchronization contract.

The OS only guarantees that the **MonitoredValueKernelCpuVa** pointer is valid for the duration of this DDI call, and not before or after it. Hence, KMD must never cache this pointer for use it elsewhere.

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_UPDATEMONITOREDVALUES**](ns-d3dkmddi-dxgkarg_updatemonitoredvalues.md)
