---
UID: NC:wdm.PO_FX_DIRECTED_POWER_UP_CALLBACK
title: PO_FX_DIRECTED_POWER_UP_CALLBACK
author: windows-driver-content
description: 
tech.root:
ms.assetid: a8980669-310f-48fa-81b7-f998aae11c98
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
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
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - wdm.h
api_name: 
 - PO_FX_DIRECTED_POWER_UP_CALLBACK
product: 
 - Windows
targetos: Windows
---

# PO_FX_DIRECTED_POWER_UP_CALLBACK callback function

## -description

Implemented by the client driver to handle driver-specific power up activities on behalf of DFx (Directed [PoFx](https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework)).

## -prototype

```
//Declaration

PO_FX_DIRECTED_POWER_UP_CALLBACK PoFxDirectedPowerUpCallback; 

// Definition

VOID PoFxDirectedPowerUpCallback 
(
	PVOID Context
	ULONG Flags
)
{...}

```

## -parameters

### -param Context: 

Supplies a pointer to the context passed in to [**PoFxRegisterDevice**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxregisterdevice).

### -param Flags: 

Reserved for future use.

## -returns

Returns VOID that ...

## -remarks

WDM drivers that register with PoFx for runtime idle power management support need to implement this callback to add DFx support.

Register your implementation of this callback function by setting the appropriate member of the [**PO_FX_DEVICE_V3**](ns-wdm-po_fx_device_v3.md) structure and then calling [**PoFxRegisterDevice**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxregisterdevice).

When Directed power up is requested, a driver will typically take following actions:

- Power itself up by requesting a D0 IRP.
- Once the D0 IRP is completed, report the device as powered ON by calling PoFxReportDevicePoweredOn(). Note this also implicitly completes the Directed power up transition back to PoFx.
- Unblock I/O queues and start processing requests normally.

Once the driver completes the Directed power up call, it can resume runtime-idle (RTD3) behavior.

The contract is very similar to S0, although no actual S-IRPs are involved (see TBD).

Note that if a device hierarchy is involved, child devices will be powered up only after the directed power framework powers up the parent device. For a given parent device, both direct children, i.e. ones enumerated by the parent, as well as any indirect children due to power relations (https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations) are considered.

## -see-also

https://review.docs.microsoft.com/en-us/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework?branch=kernel_19h1
