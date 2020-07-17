---
UID: NF:wdfdevice.WdfDeviceInitRegisterPowerPolicyStateChangeCallback
title: WdfDeviceInitRegisterPowerPolicyStateChangeCallback function (wdfdevice.h)
description: The WdfDeviceInitRegisterPowerPolicyStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's power policy state machine changes state.
old-location: wdf\wdfdeviceinitregisterpowerpolicystatechangecallback.htm
tech.root: wdf
ms.assetid: 61ddfdf9-65cf-482b-80fe-bc5a71f905cd
ms.date: 02/26/2018
keywords: ["WdfDeviceInitRegisterPowerPolicyStateChangeCallback function"]
ms.keywords: DFDeviceObjectGeneralRef_207ca167-9049-4661-baea-1a17158c3e82.xml, WdfDeviceInitRegisterPowerPolicyStateChangeCallback, WdfDeviceInitRegisterPowerPolicyStateChangeCallback method, kmdf.wdfdeviceinitregisterpowerpolicystatechangecallback, wdf.wdfdeviceinitregisterpowerpolicystatechangecallback, wdfdevice/WdfDeviceInitRegisterPowerPolicyStateChangeCallback
f1_keywords:
 - "wdfdevice/WdfDeviceInitRegisterPowerPolicyStateChangeCallback"
 - "WdfDeviceInitRegisterPowerPolicyStateChangeCallback"
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
- WdfDeviceInitRegisterPowerPolicyStateChangeCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitRegisterPowerPolicyStateChangeCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's power policy state machine changes state.


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param PowerPolicyState [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_power_policy_state">WDF_DEVICE_POWER_POLICY_STATE</a> enumerator that identifies the power policy machine state for which the driver is requesting notification.


### -param EvtDevicePowerPolicyStateChange [in]

A caller-supplied pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification">EvtDevicePowerPolicyStateChange</a> event callback function.


### -param CallbackTypes [in]

An ORed combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_state_notification_type">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


## -returns



If <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b> encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

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



If your driver calls <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.


#### Examples

The following code example registers an event callback function that the framework will call when the device's power policy state machine changes state.

```cpp
status = WdfDeviceInitRegisterPowerPolicyStateChangeCallback(
                                 DeviceInit,
                                 WdfDevStatePwrPolCheckPowerPageable,
                                 PciDrvPowerPolicyStateChangeCallback,
                                 StateNotificationAllStates
                                 );
```


