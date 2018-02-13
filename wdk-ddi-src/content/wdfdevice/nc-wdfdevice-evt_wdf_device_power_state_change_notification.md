---
UID: NC:wdfdevice.EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: A driver's EvtDevicePowerStateChange event callback function informs the driver that a device's power state machine is moving from one state to another.
old-location: wdf\evtdevicepowerstatechange.htm
old-project: wdf
ms.assetid: 9f54c7e2-0c8a-46ee-9318-6db934c1aab6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicepowerstatechange, EvtDevicePowerStateChange callback function, EvtDevicePowerStateChange, EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION, wdfdevice/EvtDevicePowerStateChange, DFDeviceObjectGeneralRef_fc945165-b31d-4d35-b3be-5586c280d8ca.xml, kmdf.evtdevicepowerstatechange
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
-	EvtDevicePowerStateChange
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDevicePowerStateChange</i> event callback function informs the driver that a device's power state machine is moving from one state to another.


## -prototype


````
EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION EvtDevicePowerStateChange;

VOID EvtDevicePowerStateChange(
  _In_ WDFDEVICE                            Device,
  _In_ PCWDF_DEVICE_POWER_NOTIFICATION_DATA NotificationData
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationData [in]

A pointer to a framework-supplied <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_notification_data.md">WDF_DEVICE_POWER_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.


## -returns



None




## -remarks



To register an <i>EvtDevicePowerStateChange</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpowerstatechangecallback.md">WdfDeviceInitRegisterPowerStateChangeCallback</a>.

Most drivers do not need to be notified when the framework's power state machine changes state. For more information, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

If the <i>EvtDevicePowerStateChange</i> callback function calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicestopidle.md">WdfDeviceStopIdle</a> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the framework's power state machine will become deadlocked.


#### Examples

To define an <i>EvtDevicePowerStateChange</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDevicePowerStateChange</i> callback function that is named <i>MyDevicePowerStateChange</i>, use the <b>EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION  MyDevicePowerStateChange;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDevicePowerStateChange (
    WDFDEVICE  Device,
    PCWDF_DEVICE_POWER_NOTIFICATION_DATA  NotificationData
 )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification.md">EvtDevicePowerPolicyStateChange</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

