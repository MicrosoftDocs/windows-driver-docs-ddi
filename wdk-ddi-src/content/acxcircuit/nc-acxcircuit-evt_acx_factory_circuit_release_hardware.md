---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
ms.date: 02/01/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback is used by the driver to add functionality when an ACXFACTORYCIRCUIT is in the release hardware phase. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: 
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
 - EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
dev_langs:
 - c++
---

## -description

The EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback is used by the driver to add functionality when an ACXFACTORYCIRCUIT is in the release hardware phase. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. (For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ResourcesTranslated

A WDF resource list that describes the translated resources to be used for the prepare hardware phase. This is a WDF framework resource-list object that represents a list of hardware resources for a device. For more information about translated resource lists, see [Raw and Translated Resources](/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

To register an EvtAcxFactoryCircuitReleaseHardware callback function, your driver must call [AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks](nf-acxcircuit-acxfactorycircuitinitsetacxcircuitpnppowercallbacks.md).

If a driver has registered an EvtAcxFactoryCircuitReleaseHardware callback function, the framework calls it during the following transitions:

- Resource rebalancing
- Orderly removal
- Surprise removal

The ACX framework calls the EvtAcxFactoryCircuitReleaseHardware callback function after the WDF framework has stopped sending I/O requests to the device, any interrupts assigned to the device have been disabled and disconnected, and the device has been turned off.

The ACX framework calls the EvtAcxFactoryCircuitReleaseHardware callback function before the WDF framework calls the driver's EvtDeviceReleaseHardware callback function.

When the framework calls the EvtAcxFactoryCircuitReleaseHardware the PDO for the device still exists and can be queried for device information that is available in the powered off state, for example PCI configuration state.

In addition, the translated hardware resources that the framework supplies to EvtDeviceReleaseHardware are still assigned to the device. The primary purpose of this callback function is to release those resources, and in particular to un-map any memory resources that the driver's EvtAcxCircuitPrepareHardware callback function mapped. The driver can also use this callback to perform any other ACXCIRCUIT management activity that might be required in the powered down state. Usually, all other hardware shutdown operations should take place in the driver's EvtDeviceD0Exit callback function.

The ACX framework always calls the driver's EvtAcxFactoryCircuitReleaseHardware callback function if the driver's EvtAcxFactoryCircuitPrepareHardware callback function has been called, unless the EvtAcxFactoryCircuitPrepareHardware returned a failure code.

For more information about when the ACX and WDF framework call these callback functions, see [PnP and Power Management Scenarios](/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios).

For more information about hardware resources, see [Introduction to Hardware Resources](/windows-hardware/drivers/wdf/introduction-to-hardware-resources).

For more information about drivers that provide this callback function, see [Supporting PnP and Power Management in Function Driver](/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers).

### Example

Example usage is shown below.

Sample pending.

```cpp

```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO
