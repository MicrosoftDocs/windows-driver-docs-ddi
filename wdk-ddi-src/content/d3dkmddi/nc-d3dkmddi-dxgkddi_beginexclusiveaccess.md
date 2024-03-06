---
UID: NC:d3dkmddi.DXGKDDI_BEGINEXCLUSIVEACCESS
title: DXGKDDI_BEGINEXCLUSIVEACCESS (d3dkmddi.h)
description: Learn more about the DXGKDDI_BEGINEXCLUSIVEACCESS callback function.
ms.date: 08/31/2023
keywords: ["DXGKDDI_BEGINEXCLUSIVEACCESS callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_BEGINEXCLUSIVEACCESS
 - d3dkmddi/DXGKDDI_BEGINEXCLUSIVEACCESS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_BEGINEXCLUSIVEACCESS
dev_langs:
 - c++
---

# DXGKDDI_BEGINEXCLUSIVEACCESS callback function

## -description

*Dxgkrnl* calls **DxgkDdiBeginExclusiveAccess** to notify the kernel-mode driver that an IOMMU domain switch is about to occur.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter.

### -param pBeginExclusiveAccess

[in] Pointer to a [**DXGKARG_BEGINEXCLUSIVEACCESS**](ns-d3dkmddi-_dxgkarg_beginexclusiveaccess.md) structure that contains the input arguments for **DxgkDdiBeginExclusiveAccess**.

## -returns

**DxgkDdiBeginExclusiveAccess** should return STATUS_SUCCESS if the operation succeeds. Otherwise, it should return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

IOMMU domain attach and detach is extremely fast, but is nonetheless not currently atomic. This means that a transaction issued over PCIe isn't guaranteed to be translated correctly while swapping to a domain with different mappings.

To handle this situation, *Dxgkrnl* calls the following KMD DDI pair:

* **DxgkDdiBeginExclusiveAccess** to notify KMD that an IOMMU domain switch is about to occur.
* [**DxgkDdiEndExclusiveAccess**](nc-d3dkmddi-dxgkddi_endexclusiveaccess.md) after the IOMMU domain switch is complete.

The driver must ensure that its hardware is silent whenever the device is switched to a new IOMMU domain. That is, the driver must ensure that it doesn't read or write to system memory from the device between these two calls.

Between these two calls, *Dxgkrnl* guarantees the following:

* The scheduler will be suspended. All active workloads will be flushed, and no new workloads will be sent to or scheduled on the hardware.
* No other DDI calls will be made.

As part of these calls, the driver may choose to disable and suppress interrupts (including vsync interrupts) for the duration of the exclusive access, even without explicit notification from the OS.

## -see-also

[**DRIVER_INITIALIZATION_DATA**](../dispmprt/ns-dispmprt-_driver_initialization_data.md)

[**DXGKARG_BEGINEXCLUSIVEACCESS**](ns-d3dkmddi-_dxgkarg_beginexclusiveaccess.md)

[**DxgkDdiEndExclusiveAccess**](nc-d3dkmddi-dxgkddi_endexclusiveaccess.md)
