---
UID: NC:wdfdevice.EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON
title: EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON
author: windows-driver-content
description: A driver's EvtDeviceArmWakeFromSxWithReason event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state.
old-location: wdf\evtdevicearmwakefromsxwithreason.htm
tech.root: wdf
ms.assetid: 8966ea8f-9760-4a09-b9d3-8fd1ac278b12
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_4d1a0d9f-ce8a-465c-afb9-0ded36c70f42.xml, EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON, EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON callback, EvtDeviceArmWakeFromSxWithReason, EvtDeviceArmWakeFromSxWithReason callback function, kmdf.evtdevicearmwakefromsxwithreason, wdf.evtdevicearmwakefromsxwithreason, wdfdevice/EvtDeviceArmWakeFromSxWithReason
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.7
req.umdf-ver: 2.0
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceArmWakeFromSxWithReason
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceArmWakeFromSxWithReason</i> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and causes the system to enter its working state (S0). 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceWakeEnabled [in]

A Boolean value that, if <b>TRUE</b>, indicates that the device's ability to wake the system is enabled. 


### -param ChildrenArmedForWake [in]

A Boolean value that, if <b>TRUE</b>, indicates that the ability of one or more child devices to wake the system is enabled.


## -returns



If the <i>EvtDeviceArmWakeFromSxWithReason</i> callback function encounters no error, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/79bf7a42-5053-428a-a78b-dd8bdff93a69">EvtDeviceDisarmWakeFromSx</a> callback function. (The framework does not report a device failure to the PnP manager.) 




## -remarks



Version 1.7 and later versions of KMDF support the <i>EvtDeviceArmWakeFromSxWithReason</i> callback function in addition to the <a href="https://msdn.microsoft.com/4954a278-8470-402c-a8ba-5e46ca56ddf7">EvtDeviceArmWakeFromSx</a> callback function.

To register an <i>EvtDeviceArmWakeFromSxWithReason</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>. Drivers can register either an <a href="https://msdn.microsoft.com/4954a278-8470-402c-a8ba-5e46ca56ddf7">EvtDeviceArmWakeFromSx</a> callback function or an <i>EvtDeviceArmWakeFromSxWithReason</i> callback function, but not both.

The <i>EvtDeviceArmWakeFromSxWithReason</i> callback function provides two parameters that enable the driver to determine why the framework has called it:

<ul>
<li>
The framework sets the <i>DeviceWakeEnabled</i> parameter to <b>TRUE</b> if the <b>Enabled</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551277">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure indicates that the device can wake the system.

</li>
<li>
The framework sets the <i>ChildrenArmedForWake</i> parameter to <b>TRUE</b> if one or more of the device's child devices can wake the system and the <b>ArmForWakeIfChildrenAreArmedForWake</b> member of WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS is set to <b>TRUE</b>.

</li>
</ul>
Either one or both of these parameters can be <b>TRUE</b>, because of the following scenarios:

<ul>
<li>
The driver's device is enabled to wake the system.

</li>
<li>
One or more of the device's child devices are enabled to wake the system.

</li>
<li>
Both the device and one or more of its child devices are enabled to wake the system.

</li>
</ul>
For more information about the <i>EvtDeviceArmWakeFromSxWithReason</i> callback function, see the Remarks section of <a href="https://msdn.microsoft.com/4954a278-8470-402c-a8ba-5e46ca56ddf7">EvtDeviceArmWakeFromSx</a>.


#### Examples

To define an <i>EvtDeviceArmWakeFromSxWithReason</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceArmWakeFromSxWithReason</i> callback function that is named <i>MyDeviceArmWakeFromSxWithReason</i>, use the <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON  MyDeviceArmWakeFromSxWithReason;</pre>
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
 NTSTATUS
 MyDeviceArmWakeFromSxWithReason (
    WDFDEVICE  Device
    BOOLEAN  DeviceWakeEnabled,
    BOOLEAN  ChildrenArmedForWake
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_ARM_WAKE_FROM_SX_WITH_REASON</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/a3579239-517f-4df0-a632-31e1176c6552">EvtDeviceArmWakeFromS0</a>



<a href="https://msdn.microsoft.com/4954a278-8470-402c-a8ba-5e46ca56ddf7">EvtDeviceArmWakeFromSx</a>



<a href="https://msdn.microsoft.com/79bf7a42-5053-428a-a78b-dd8bdff93a69">EvtDeviceDisarmWakeFromSx</a>
 

 

