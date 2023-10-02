---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN
ms.date: 12/14/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN callback is used by the driver to add functionality in the power down path of an ACXFACTORYCIRCUIT object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - acxcircuit.h
api_name:
 - EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN
dev_langs:
 - c++
---

## -description

The **EVT_ACX_FACTORY_CIRCUIT_POWER_DOWN** callback is used by the driver to add functionality in the power down path of an ACXFACTORYCIRCUIT object.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param TargetState

A [WDF_POWER_DEVICE_STATE enumeration](/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state) that identifies the target device power state.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

To register an EvtAcxFactoryCircuitPrepareHardware callback function, a driver must call [AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks](nf-acxcircuit-acxfactorycircuitinitsetacxcircuitpnppowercallbacks.md).

If the driver has registered an EvtCircuitPowerDown callback function, the ACX framework calls the function each time one of the driver's devices leaves its working (D0) state. A device leaves the D0 state when one of the following occurs:

- The system and all of its devices are about to leave their working states and enter a low-power state.
- The device is about to enter a low-power state because it is idle, if the device supports low-power idle.
- The Plug and Play manager is attempting to redistribute the system's hardware resources.
- A user has indicated, typically by means of an application's user interface, that he or she wants to remove the device.
- The framework also calls the EvtFactoryCircuitPowerDown callback function after a device has been removed unexpectedly (surprise-removed).

For more information about when the framework calls this callback function, see [PnP and Power Management Scenarios](/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios).

Unless the device has been surprise-removed, the ACX framework calls this callback function immediately after it disables the device's interrupts, but before the device's power is reduced from D0 and before WDF invokes the driver's EvtDeviceD0Exit callback on the associated devices. The TargetState parameter identifies the device power state that the device is about to enter.

The EvtFactoryCircuitPowerDown callback function must perform any operations that are necessary before the ACXFACTORYCIRCUT's hardware enters the specified low-power state, such as saving any information that the driver will need later to restore the ACXFACTORYCIRCUIT's hardware to its D0 power state.

If TargetState is WdfPowerDeviceD3Final, you should assume that the system is being turned off, the associated device is about to be removed, or a resource rebalance is in progress. If your driver must save information, it should write it to disk or some other permanent storage medium.

For more information about drivers that provide this callback function, see 
[Supporting PnP and Power Management in Function Driver](/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers).

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
