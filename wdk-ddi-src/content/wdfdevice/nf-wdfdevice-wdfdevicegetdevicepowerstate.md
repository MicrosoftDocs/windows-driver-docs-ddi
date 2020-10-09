---
UID: NF:wdfdevice.WdfDeviceGetDevicePowerState
title: WdfDeviceGetDevicePowerState function (wdfdevice.h)
description: The WdfDeviceGetDevicePowerState method returns the current state of the framework's power state machine, for a specified device.
old-location: wdf\wdfdevicegetdevicepowerstate.htm
tech.root: wdf
ms.assetid: 7405e0c7-9263-4911-9b1e-52cffa559af3
ms.date: 02/26/2018
keywords: ["WdfDeviceGetDevicePowerState function"]
ms.keywords: DFDeviceObjectGeneralRef_40013978-2c8d-4776-b218-5f0c743e57e9.xml, WdfDeviceGetDevicePowerState, WdfDeviceGetDevicePowerState method, kmdf.wdfdevicegetdevicepowerstate, wdf.wdfdevicegetdevicepowerstate, wdfdevice/WdfDeviceGetDevicePowerState
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceGetDevicePowerState
 - wdfdevice/WdfDeviceGetDevicePowerState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceGetDevicePowerState
---

# WdfDeviceGetDevicePowerState function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This function is for Microsoft-internal use only.

The <b>WdfDeviceGetDevicePowerState</b> method returns the current state of the framework's power state machine, for a specified device.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -returns

<b>WdfDeviceGetDevicePowerState</b> returns a <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_power_state">WDF_DEVICE_POWER_STATE</a>-typed enumerator that identifies the current state of the framework's power state machine for the specified device. 

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about the framework's state machines, see <a href="/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.

The <b>WdfDeviceGetDevicePowerState</b> method returns a meaningful value only if it is called from within the following callback functions:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled">EvtDeviceD0EntryPostInterruptsEnabled</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled">EvtDeviceD0ExitPreInterruptsDisabled</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>


</li>
</ul>

#### Examples

The following code example obtains the current state of the framework's power state machine for a specified device.

```cpp
WDF_DEVICE_POWER_STATE state;

state = WdfDeviceGetDevicePowerState(Device);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevstatenormalize">WdfDevStateNormalize</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepnpstate">WdfDeviceGetDevicePnpState</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerpolicystate">WdfDeviceGetDevicePowerPolicyState</a>