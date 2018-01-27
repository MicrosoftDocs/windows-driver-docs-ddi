---
UID: NC:wdfdevice.EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: A driver's EvtDevicePowerPolicyStateChange event callback function informs the driver that a device's power policy state machine is moving from one state to another.
old-location: wdf\evtdevicepowerpolicystatechange.htm
old-project: wdf
ms.assetid: 91432773-3255-4feb-a6f4-c24da4486703
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicepowerpolicystatechange, EvtDevicePowerPolicyStateChange callback function, EvtDevicePowerPolicyStateChange, EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION, wdfdevice/EvtDevicePowerPolicyStateChange, DFDeviceObjectGeneralRef_e672bc5b-0c7a-4df4-8c21-d3f6aafa6fb8.xml, kmdf.evtdevicepowerpolicystatechange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdfdevice.h
apiname: 
-	EvtDevicePowerPolicyStateChange
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDevicePowerPolicyStateChange</i> event callback function informs the driver that a device's power policy state machine is moving from one state to another.


## -prototype


````
EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION EvtDevicePowerPolicyStateChange;

VOID EvtDevicePowerPolicyStateChange(
  _In_ WDFDEVICE                                   Device,
  _In_ PCWDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA NotificationData
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationData [in]

A pointer to a framework-supplied <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_notification_data.md">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.


## -returns


None



## -remarks


To register an <i>EvtDevicePowerPolicyStateChange</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback.md">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>.

Most drivers do not need to be notified when the framework's power policy state machine changes state. For more information, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

If the <i>EvtDevicePowerPolicyStateChange</i> callback function calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicestopidle.md">WdfDeviceStopIdle</a> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the framework's power policy state machine will become deadlocked.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_power_state_change_notification.md">EvtDevicePowerStateChange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

