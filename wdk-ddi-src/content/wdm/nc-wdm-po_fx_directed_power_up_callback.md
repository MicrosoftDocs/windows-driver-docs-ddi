---
UID: NC:wdm.PO_FX_DIRECTED_POWER_UP_CALLBACK
title: PO_FX_DIRECTED_POWER_UP_CALLBACK (wdm.h)
description: The PO_FX_DIRECTED_POWER_UP_CALLBACK callback function is implemented by the client driver to handle driver-specific power up activities on behalf of DFx.
tech.root: kernel
ms.date: 01/19/2023
keywords: ["PO_FX_DIRECTED_POWER_UP_CALLBACK callback function"]
req.header: wdm.h
req.include-header: Wdm.h
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

## -description

The PO_FX_DIRECTED_POWER_UP_CALLBACK callback function is implemented by the client driver to handle driver-specific power up activities on behalf of DFx (Directed [PoFx](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework)).

## -parameters

### -param Context

Supplies a pointer to the context passed in to [**PoFxRegisterDevice**](./nf-wdm-pofxregisterdevice.md).

### -param Flags

Reserved for future use.

## -remarks

WDM drivers that register with PoFx for runtime idle power management support need to implement this callback to add DFx support.

Register your implementation of this callback function by setting the appropriate member of the [**PO_FX_DEVICE_V3**](ns-wdm-po_fx_device_v3.md) structure and then calling [**PoFxRegisterDevice**](./nf-wdm-pofxregisterdevice.md).

This callback is invoked when the system determines the device needs to power up after having previously being powered down in the [*PO_FX_DIRECTED_POWER_DOWN_CALLBACK*](./nc-wdm-po_fx_directed_power_down_callback.md) callback function. The device may need to be powered up when the system exits Modern Standby, [activators](/windows-hardware/design/device-experiences/activators) start to run, or a hardware-initiated wake occurs.

When this callback is invoked, the driver typically performs the following high-level tasks:

- Request a D0 IRP to power up the device.

- After the D0 IRP completes, call [**PoFxReportDevicePoweredOn**](./nf-wdm-pofxreportdevicepoweredon.md).

- Unblock I/O queues and start processing requests normally.

Once the driver completes the Directed power up call, it can resume runtime-idle (RTD3) behavior.

The contract is very similar to S0, although no S-IRPs are involved.

Note that if a device hierarchy is involved, the directed power framework asks the child devices to power down before the parent device.  For a given parent device, direct children (ones enumerated by the parent) and indirect children due to [power relations](/windows-hardware/drivers/kernel/irp-mn-query-device-relations) are considered.

## -see-also

[Introduction to the Directed Power Management Framework](/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework)

[PO_FX_DIRECTED_POWER_DOWN_CALLBACK](nc-wdm-po_fx_directed_power_down_callback.md)
