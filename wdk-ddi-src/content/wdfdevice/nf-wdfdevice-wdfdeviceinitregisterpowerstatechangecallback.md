---
UID: NF:wdfdevice.WdfDeviceInitRegisterPowerStateChangeCallback
title: WdfDeviceInitRegisterPowerStateChangeCallback function (wdfdevice.h)
description: The WdfDeviceInitRegisterPowerStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's power state machine changes state.
old-location: wdf\wdfdeviceinitregisterpowerstatechangecallback.htm
tech.root: wdf
ms.assetid: f3c09dfb-d327-488b-8e5d-77a579d1e1f0
ms.date: 02/26/2018
keywords: ["WdfDeviceInitRegisterPowerStateChangeCallback function"]
ms.keywords: DFDeviceObjectGeneralRef_c2199058-308e-4207-b035-30de28c64fa5.xml, WdfDeviceInitRegisterPowerStateChangeCallback, WdfDeviceInitRegisterPowerStateChangeCallback method, kmdf.wdfdeviceinitregisterpowerstatechangecallback, wdf.wdfdeviceinitregisterpowerstatechangecallback, wdfdevice/WdfDeviceInitRegisterPowerStateChangeCallback
f1_keywords:
 - "wdfdevice/WdfDeviceInitRegisterPowerStateChangeCallback"
 - "WdfDeviceInitRegisterPowerStateChangeCallback"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceInitRegisterPowerStateChangeCallback
targetos: Windows
req.typenames: 
---

# WdfDeviceInitRegisterPowerStateChangeCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitRegisterPowerStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's power state machine changes state.


## -parameters




### -param DeviceInit 
[in]
A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param PowerState 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_power_state">WDF_DEVICE_POWER_STATE</a> enumerator that identifies the power machine state for which the driver is requesting notification.


### -param EvtDevicePowerStateChange 
[in]
A caller-supplied pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_power_state_change_notification">EvtDevicePowerStateChange</a> event callback function.


### -param CallbackTypes 
[in]
An ORed combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_state_notification_type">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


## -returns



If the operation succeeds, <b>WdfDeviceInitRegisterPowerStateChangeCallback</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
</table>
 




## -remarks



If your driver calls <b>WdfDeviceInitRegisterPowerStateChangeCallback</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.


#### Examples

The following code example registers an event callback function that the framework will call when the device's power state machine changes state.

```cpp
status = WdfDeviceInitRegisterPowerStateChangeCallback(
                                     DeviceInit,
                                     WdfDevStatePowerD0StartingConnectInterrupt,
                                     PciDrvPowerStateChangeCallback,
                                     StateNotificationAllStates
                                     );
```


