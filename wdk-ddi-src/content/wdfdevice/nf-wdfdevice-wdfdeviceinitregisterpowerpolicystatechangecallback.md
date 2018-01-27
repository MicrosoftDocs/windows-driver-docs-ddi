---
UID: NF:wdfdevice.WdfDeviceInitRegisterPowerPolicyStateChangeCallback
title: WdfDeviceInitRegisterPowerPolicyStateChangeCallback function
author: windows-driver-content
description: The WdfDeviceInitRegisterPowerPolicyStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's power policy state machine changes state.
old-location: wdf\wdfdeviceinitregisterpowerpolicystatechangecallback.htm
old-project: wdf
ms.assetid: 61ddfdf9-65cf-482b-80fe-bc5a71f905cd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEINITREGISTERPOWERPOLICYSTATECHANGECALLBACK, DFDeviceObjectGeneralRef_207ca167-9049-4661-baea-1a17158c3e82.xml, WdfDeviceInitRegisterPowerPolicyStateChangeCallback method, wdf.wdfdeviceinitregisterpowerpolicystatechangecallback, wdfdevice/WdfDeviceInitRegisterPowerPolicyStateChangeCallback, WdfDeviceInitRegisterPowerPolicyStateChangeCallback, kmdf.wdfdeviceinitregisterpowerpolicystatechangecallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname: 
-	WdfDeviceInitRegisterPowerPolicyStateChangeCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitRegisterPowerPolicyStateChangeCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's power policy state machine changes state.


## -syntax


````
NTSTATUS WdfDeviceInitRegisterPowerPolicyStateChangeCallback(
  _In_ PWDFDEVICE_INIT                                       DeviceInit,
  _In_ WDF_DEVICE_POWER_POLICY_STATE                         PowerPolicyState,
  _In_ PFN_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION EvtDevicePowerPolicyStateChange,
  _In_ ULONG                                                 CallbackTypes
);
````


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param PowerPolicyState [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_power_policy_state.md">WDF_DEVICE_POWER_POLICY_STATE</a> enumerator that identifies the power policy machine state for which the driver is requesting notification.


### -param EvtDevicePowerPolicyStateChange [in]

A caller-supplied pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification.md">EvtDevicePowerPolicyStateChange</a> event callback function.


### -param CallbackTypes [in]

An ORed combination of <a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


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


If your driver calls <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about <b>WdfDeviceInitRegisterPowerPolicyStateChangeCallback</b>, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.


