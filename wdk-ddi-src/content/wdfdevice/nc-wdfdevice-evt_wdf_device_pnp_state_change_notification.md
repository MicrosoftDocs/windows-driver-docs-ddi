---
UID: NC:wdfdevice.EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: A driver's EvtDevicePnpStateChange event callback function informs the driver that a device's Plug and Play (PnP) state machine is moving from one state to another.
old-location: wdf\evtdevicepnpstatechange.htm
old-project: wdf
ms.assetid: 5f08d331-0e58-45a3-93a3-b5e9a40b5af3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicepnpstatechange, EvtDevicePnpStateChange callback function, EvtDevicePnpStateChange, EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION, wdfdevice/EvtDevicePnpStateChange, DFDeviceObjectGeneralRef_484dd3d0-689b-4c81-bdc2-85d14db47499.xml, kmdf.evtdevicepnpstatechange
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
-	EvtDevicePnpStateChange
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDevicePnpStateChange</i> event callback function informs the driver that a device's Plug and Play (PnP) state machine is moving from one state to another.


## -prototype


````
EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION EvtDevicePnpStateChange;

VOID EvtDevicePnpStateChange(
  _In_ WDFDEVICE                          Device,
  _In_ PCWDF_DEVICE_PNP_NOTIFICATION_DATA NotificationData
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationData [in]

A pointer to a framework-supplied <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_pnp_notification_data.md">WDF_DEVICE_PNP_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.


## -returns


None



## -remarks


To register an <i>EvtDevicePnpStateChange</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback.md">WdfDeviceInitRegisterPnpStateChangeCallback</a>.

Most drivers do not need to be notified when the framework's PnP state machine changes state. For more information about the framework's PnP state machine, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification.md">EvtDevicePowerPolicyStateChange</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_power_state_change_notification.md">EvtDevicePowerStateChange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

