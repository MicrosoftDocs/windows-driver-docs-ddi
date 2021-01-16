---
UID: NE:wdfdevice._WDF_STATE_NOTIFICATION_TYPE
title: _WDF_STATE_NOTIFICATION_TYPE (wdfdevice.h)
description: The WDF_STATE_NOTIFICATION_TYPE enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive.
old-location: wdf\wdf_state_notification_type.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_STATE_NOTIFICATION_TYPE enumeration"]
ms.keywords: DFDeviceObjectGeneralRef_c1bdabfc-dd89-4eeb-b5ba-9f03a65414c5.xml, StateNotificationAllStates, StateNotificationEnterState, StateNotificationInvalid, StateNotificationLeaveState, StateNotificationPostProcessState, WDF_STATE_NOTIFICATION_TYPE, WDF_STATE_NOTIFICATION_TYPE enumeration, _WDF_STATE_NOTIFICATION_TYPE, kmdf.wdf_state_notification_type, wdf.wdf_state_notification_type, wdfdevice/StateNotificationAllStates, wdfdevice/StateNotificationEnterState, wdfdevice/StateNotificationInvalid, wdfdevice/StateNotificationLeaveState, wdfdevice/StateNotificationPostProcessState, wdfdevice/WDF_STATE_NOTIFICATION_TYPE
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
f1_keywords:
 - _WDF_STATE_NOTIFICATION_TYPE
 - wdfdevice/_WDF_STATE_NOTIFICATION_TYPE
 - WDF_STATE_NOTIFICATION_TYPE
 - wdfdevice/WDF_STATE_NOTIFICATION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_STATE_NOTIFICATION_TYPE
 - WDF_STATE_NOTIFICATION_TYPE
---

# _WDF_STATE_NOTIFICATION_TYPE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This enumeration is for Microsoft internal use only.

The <b>WDF_STATE_NOTIFICATION_TYPE</b> enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive.

## -enum-fields

### -field StateNotificationInvalid

For internal use only.

### -field StateNotificationEnterState

The driver is notified immediately before a device's Plug and Play, power, or power policy state machine enters a specified state.

### -field StateNotificationPostProcessState

The driver is notified immediately after a device's Plug and Play, power, or power policy state machine enters a specified state.

### -field StateNotificationLeaveState

The driver is notified immediately before a device's Plug and Play, power, or power policy state machine leaves a specified state.

### -field StateNotificationAllStates

The driver receives enter-state, postprocess-state, and leave-state notifications.

## -remarks

When the framework's state machine for a driver's device changes from state <i>a</i> to state <i>b</i>, the framework notifies the driver (if the driver registered an appropriate event callback function), in the following sequence:

<ol>
<li>
Calls state <i>a</i>'s leave-state notification callback function.

</li>
<li>
Calls state <i>b</i>'s enter-state notification callback function.

</li>
<li>
Changes the device's state from <i>a</i> to <i>b</i>.

</li>
<li>
Calls state <i>b</i>'s postprocess-state notification callback function.

</li>
</ol>
To register for notification of a change in state, the driver can call the following methods:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback">WdfDeviceInitRegisterPnpStateChangeCallback</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpowerstatechangecallback">WdfDeviceInitRegisterPowerStateChangeCallback</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>


</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_notification_data">WDF_DEVICE_PNP_NOTIFICATION_DATA</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_notification_data">WDF_DEVICE_POWER_NOTIFICATION_DATA</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_notification_data">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a>

