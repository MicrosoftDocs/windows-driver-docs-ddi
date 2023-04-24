---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE
ms.date: 12/14/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE callback is used by the driver to add functionality when a circuit factory is in the prepare hardware phase.
prerelease: true
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
 - EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_FACTORY_CIRCUIT_PREPARE_HARDWARE** callback is used by the driver to add functionality when a circuit factory is in the prepare hardware phase.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ResourcesRaw

A WDF resource list that describes the raw resources to be used for the prepare hardware phase. This is a WDF framework resource-list object that represents a list of hardware resources for a device. For more information about raw resources, see [Hardware Resources for Framework-Based Drivers](/windows-hardware/drivers/wdf/raw-and-translated-resources).

### -param ResourcesTranslated

A WDF resource list that describes the translated resources to be used for the prepare hardware phase. This is a WDF framework resource-list object that represents a list of hardware resources for a device. For more information about translated resource lists, see [Raw and Translated Resources](/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

To register an EvtAcxFactoryCircuitPrepareHardware callback function, a driver must call the [AcxFactoryCircuitInitSetAcxCircuitPnpPowerCallbacks method](nf-acxcircuit-acxfactorycircuitinitsetacxcircuitpnppowercallbacks.md).

If the driver has registered an EvtAcxFactoryCircuitPrepareHardware callback function for an ACXFACTORYCIRCUIT, the ACX framework calls the function after WDF framework calls the driver's EvtDevicePrepareHardware callback function.

The EvtAcxFactoryCircuitPrepareHardware callback function accesses the device's raw and translated hardware resources by using the ResourcesRaw and ResourcesTranslated handles that it receives. The callback function can call [WdfCmResourceListGetCount](/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistgetcount) and [WdfCmResourceListGetDescriptor](/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistgetdescriptor) to traverse the resource lists. This callback function cannot modify the resource lists.

For more information about resource lists and the order in which the resources appear, see  [Raw and Translated Resources](/windows-hardware/drivers/wdf/raw-and-translated-resources).

Typically, your driver's EvtAcxFactoryCircuitPrepareHardware callback function does the following, if necessary:

- Maps physical memory addresses to virtual addresses of the ACXFACTORYCIRCUIT so the driver can access memory that is assigned to the device.
- Optionally, your driver's EvtAcxFactoryCircuitPrepareHardware callback function might queue a work item to complete any other time-intensive configuration tasks. Using a work item for such operations can help ensure that your device's start up time does not increase the system boot time. For more information, see [Using Framework Work Items](/windows-hardware/drivers/wdf/using-framework-work-items).
- Typically, all other hardware initialization operations, including loading firmware, should take place each time that the device enters its working (D0) state and should therefore take place in the driver's EvtDeviceD0Entry callback function.

The ResourcesRaw and ResourcesTranslated handles that the EvtAcxCircuitPrepareHardware/EvtDevicePrepareHardware callback function receives remain valid until the driver's EvtDeviceReleaseHardware callback function returns.

If the driver fails the EvtAcxFactoryCircuitPrepareHardware callback, the ACXFACTORYCIRCUIT object is placed in the delete-pending state.

For more information about hardware resources, see [Introduction to Hardware Resources](/windows-hardware/drivers/wdf/introduction-to-hardware-resources).

For more information about when the ACX and WDF framework call these callback functions, see [PnP and Power Management Scenarios](/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios).

For more information about drivers that provide this callback function, see [Supporting PnP and Power Management in Function Driver](/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers).

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
