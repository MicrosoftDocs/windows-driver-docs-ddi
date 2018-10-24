---
UID: NC:wdfdevice.EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED
title: EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED
author: windows-driver-content
description: A driver's EvtDeviceWakeFromS0Triggered event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.
old-location: wdf\evtdevicewakefroms0triggered.htm
tech.root: wdf
ms.assetid: 4395b1c1-ae67-42fc-b6c7-b1bdbf090c5b
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d5f1f5da-3fa1-4d26-ab15-587b66c7d5c2.xml, EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED, EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED callback, EvtDeviceWakeFromS0Triggered, EvtDeviceWakeFromS0Triggered callback function, kmdf.evtdevicewakefroms0triggered, wdf.evtdevicewakefroms0triggered, wdfdevice/EvtDeviceWakeFromS0Triggered
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
-	EvtDeviceWakeFromS0Triggered
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceWakeFromS0Triggered</i> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



None




## -remarks



To register an <i>EvtDeviceWakeFromS0Triggered</i> callback function, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered  this callback, the framework calls it after calling the driver's <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function and before calling the driver's <a href="https://msdn.microsoft.com/e944c299-d0b4-4ee3-8f46-0458807e4cee">EvtDeviceDisarmWakeFromS0</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <i>EvtDeviceWakeFromS0Triggered</i> callback function will not be called even though the driver's device triggered a wake signal.

Some buses combine wake signals from several children. If your device is connected to one of these buses, the callback function might have to determine if the current device triggered the wake-up signal. If your device provides a hardware latch that saves the device's triggered state, it is best to check that state in the driver's <a href="https://msdn.microsoft.com/e944c299-d0b4-4ee3-8f46-0458807e4cee">EvtDeviceDisarmWakeFromS0</a> callback function, because that callback is always called after the device wakes up, even if the wake signal was dropped.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.


#### Examples

To define an <i>EvtDeviceWakeFromS0Triggered</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWakeFromS0Triggered</i> callback function that is named <i>MyDeviceWakeFromS0Triggered</i>, use the <b>EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED  MyDeviceWakeFromS0Triggered;</pre>
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
 MyDeviceWakeFromS0Triggered (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_WAKE_FROM_S0_TRIGGERED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/a3579239-517f-4df0-a632-31e1176c6552">EvtDeviceArmWakeFromS0</a>



<a href="https://msdn.microsoft.com/e944c299-d0b4-4ee3-8f46-0458807e4cee">EvtDeviceDisarmWakeFromS0</a>



<a href="https://msdn.microsoft.com/a1899d90-4906-458d-b7e3-122655f4d926">EvtDeviceWakeFromSxTriggered</a>
 

 

