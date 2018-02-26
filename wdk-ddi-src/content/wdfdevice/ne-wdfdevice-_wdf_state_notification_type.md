---
UID: NE:wdfdevice._WDF_STATE_NOTIFICATION_TYPE
title: "_WDF_STATE_NOTIFICATION_TYPE"
author: windows-driver-content
description: The WDF_STATE_NOTIFICATION_TYPE enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive.
old-location: wdf\wdf_state_notification_type.htm
old-project: wdf
ms.assetid: fc44c970-482c-4fbf-a149-e6b732f6c9d8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, A, C, D, DFDeviceObjectGeneralRef_c1bdabfc-dd89-4eeb-b5ba-9f03a65414c5.xml, E, F, I, N, O, P, S, StateNotificationAllStates, StateNotificationEnterState, StateNotificationInvalid, StateNotificationLeaveState, StateNotificationPostProcessState, T, W, WDF_STATE_NOTIFICATION_TYPE, WDF_STATE_NOTIFICATION_TYPE enumeration, Y, _, _WDF_STATE_NOTIFICATION_TYPE, kmdf.wdf_state_notification_type, wdf.wdf_state_notification_type, wdfdevice/StateNotificationAllStates, wdfdevice/StateNotificationEnterState, wdfdevice/StateNotificationInvalid, wdfdevice/StateNotificationLeaveState, wdfdevice/StateNotificationPostProcessState, wdfdevice/WDF_STATE_NOTIFICATION_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_STATE_NOTIFICATION_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# _WDF_STATE_NOTIFICATION_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_STATE_NOTIFICATION_TYPE</b> enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive.


## -syntax


````
typedef enum _WDF_STATE_NOTIFICATION_TYPE { 
  StateNotificationInvalid           = 0x0000,
  StateNotificationEnterState        = 0x0001,
  StateNotificationPostProcessState  = 0x0002,
  StateNotificationLeaveState        = 0x0004,
  StateNotificationAllStates         = StateNotificationEnterState | StateNotificationPostProcessState | StateNotificationLeaveState
} WDF_STATE_NOTIFICATION_TYPE;
````


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

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback.md">WdfDeviceInitRegisterPnpStateChangeCallback</a>


</li>
<li>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpowerstatechangecallback.md">WdfDeviceInitRegisterPowerStateChangeCallback</a>


</li>
<li>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback.md">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>


</li>
</ul>



## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_notification_data.md">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a>



<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_notification_data.md">WDF_DEVICE_POWER_NOTIFICATION_DATA</a>



<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_pnp_notification_data.md">WDF_DEVICE_PNP_NOTIFICATION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_STATE_NOTIFICATION_TYPE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

