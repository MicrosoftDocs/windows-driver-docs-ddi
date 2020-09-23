---
UID: NC:wdm.PO_FX_DIRECTED_POWER_UP_CALLBACK
title: PO_FX_DIRECTED_POWER_UP_CALLBACK
description: 
tech.root: 
ms.assetid: a8980669-310f-48fa-81b7-f998aae11c98
ms.author: windowsdriverdev
ms.date: 08/19/2019
keywords: ["PO_FX_DIRECTED_POWER_UP_CALLBACK callback function"]
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
 - PO_FX_DIRECTED_POWER_UP_CALLBACK
 - wdm/PO_FX_DIRECTED_POWER_UP_CALLBACK
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
---

# PO_FX_DIRECTED_POWER_UP_CALLBACK callback function


## -description

Implemented by the client driver to handle driver-specific power up activities on behalf of DFx (Directed [PoFx](https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework)).

## -parameters

### -param Context: 

Supplies a pointer to the context passed in to [**PoFxRegisterDevice**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice).

### -param Flags: 

Reserved for future use.

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

## -remarks

WDM drivers that register with PoFx for runtime idle power management support need to implement this callback to add DFx support.

Register your implementation of this callback function by setting the appropriate member of the [**PO_FX_DEVICE_V3**](ns-wdm-po_fx_device_v3.md) structure and then calling [**PoFxRegisterDevice**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice).

When this callback is invoked, the driver typically performs the following high-level tasks:

- Request a D0 IRP to power up the device.
- After the D0 IRP completes, call [**PoFxReportDevicePoweredOn**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxreportdevicepoweredon).
- Unblock I/O queues and start processing requests normally.

Once the driver completes the Directed power up call, it can resume runtime-idle (RTD3) behavior.

The contract is very similar to S0, although no S-IRPs are involved.

Note that if a device hierarchy is involved, the directed power framework asks the child devices to power down before the parent device.  For a given parent device, direct children (ones enumerated by the parent) and indirect children due to [power relations](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations) are considered.

## -see-also

- [Introduction to the Directed Power Management Framework](https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework)
- [PO_FX_DIRECTED_POWER_DOWN_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_directed_power_down_callback_

