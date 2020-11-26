---
UID: NC:wdm.PO_FX_DIRECTED_POWER_DOWN_CALLBACK
title: PO_FX_DIRECTED_POWER_DOWN_CALLBACK
description: 
tech.root: kernel
ms.assetid: d4d5aca2-8de7-4cb5-8626-77b0dda843bd
ms.date: 08/19/2019
keywords: ["PO_FX_DIRECTED_POWER_DOWN_CALLBACK callback function"]
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
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
 - PO_FX_DIRECTED_POWER_DOWN_CALLBACK
 - wdm/PO_FX_DIRECTED_POWER_DOWN_CALLBACK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PO_FX_DIRECTED_POWER_DOWN_CALLBACK
product:
 - Windows
---

# PO_FX_DIRECTED_POWER_DOWN_CALLBACK callback function


## -description

Implemented by the client driver to handle driver-specific power down activities on behalf of DFx (Directed [PoFx](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework)).

## -parameters

### -param Context: 

Supplies a pointer to the context passed in to [**PoFxRegisterDevice**](./nf-wdm-pofxregisterdevice.md).

### -param Flags: 

Reserved for future use.

## -prototype

```
//Declaration

PO_FX_DIRECTED_POWER_DOWN_CALLBACK PoFxDirectedPowerDownCallback; 

// Definition

VOID PoFxDirectedPowerDownCallback 
(
	PVOID Context
	ULONG Flags
)
{...}

```

## -remarks

WDM drivers that register with PoFx for runtime idle power management support need to implement this callback to add DFx support.

Register your implementation of this callback function by setting the appropriate member of the [**PO_FX_DEVICE_V3**](ns-wdm-po_fx_device_v3.md) structure and then calling [**PoFxRegisterDevice**](./nf-wdm-pofxregisterdevice.md).

When this callback is invoked, the driver typically performs the following high-level tasks:

- Stop processing new work.
- Transition into low-power state immediately.
- Remain in low-power state until the system calls the driver's [PO_FX_DIRECTED_POWER_UP_CALLBACK](./nc-wdm-po_fx_directed_power_up_callback.md).

Implementation steps and order may vary, but might include some of the following:

- Request a Dx IRP.
- After the Dx IRP arrives, block I/O queues.
- Wait for in-progress operations to complete.
- If those operations are taking too long, optionally cancel them.
- Perform actions necessary to transition the device into Dx (for example save hardware state).
- Arm for wake as necessary.
- Call [**PoFxCompleteDirectedPowerDown**](./nf-wdm-pofxcompletedirectedpowerdown.md).
- Remain in Dx until the system calls [PO_FX_DIRECTED_POWER_UP_CALLBACK](./nc-wdm-po_fx_directed_power_up_callback.md).

The contract is very similar to S3/S4, although no S-IRPs are involved.

Note that if a device hierarchy is involved, the directed power framework asks the child devices to power down before the parent device.  For a given parent device, direct children (ones enumerated by the parent) and indirect children due to [power relations](/windows-hardware/drivers/kernel/irp-mn-query-device-relations) are considered.

## -see-also

- [Introduction to the Directed Power Management Framework](/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework)
- [PO_FX_DIRECTED_POWER_UP_CALLBACK](./nc-wdm-po_fx_directed_power_up_callback.md)