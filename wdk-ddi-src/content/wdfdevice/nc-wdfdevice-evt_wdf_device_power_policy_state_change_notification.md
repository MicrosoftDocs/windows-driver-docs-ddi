---
UID: NC:wdfdevice.EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION (wdfdevice.h)
description: A driver's EvtDevicePowerPolicyStateChange event callback function informs the driver that a device's power policy state machine is moving from one state to another.
old-location: wdf\evtdevicepowerpolicystatechange.htm
tech.root: wdf
ms.assetid: 91432773-3255-4feb-a6f4-c24da4486703
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e672bc5b-0c7a-4df4-8c21-d3f6aafa6fb8.xml, EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback, EvtDevicePowerPolicyStateChange, EvtDevicePowerPolicyStateChange callback function, kmdf.evtdevicepowerpolicystatechange, wdf.evtdevicepowerpolicystatechange, wdfdevice/EvtDevicePowerPolicyStateChange
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDevicePowerPolicyStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This callback function is for Microsoft-internal use only.

A driver's <i>EvtDevicePowerPolicyStateChange</i> event callback function informs the driver that a device's power policy state machine is moving from one state to another.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationData [in]

A pointer to a framework-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_notification_data">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.


## -returns



None




## -remarks



To register an <i>EvtDevicePowerPolicyStateChange</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.

If the <i>EvtDevicePowerPolicyStateChange</i> callback function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the framework's power policy state machine will become deadlocked.


#### Examples

To define an <i>EvtDevicePowerPolicyStateChange</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDevicePowerPolicyStateChange</i> callback function that is named <i>MyDevicePowerPolicyStateChange</i>, use the <b>EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION  MyDevicePowerPolicyStateChange;</pre>
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
 MyDevicePowerPolicyStateChange (
    WDFDEVICE  Device,
    PCWDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA  NotificationData
 )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_POWER_POLICY_STATE_CHANGE_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_pnp_state_change_notification">EvtDevicePnpStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_power_state_change_notification">EvtDevicePowerStateChange</a>
 

 

