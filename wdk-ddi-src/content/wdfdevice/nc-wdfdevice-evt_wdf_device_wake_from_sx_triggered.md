---
UID: NC:wdfdevice.EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED
title: EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED (wdfdevice.h)
description: A driver's EvtDeviceWakeFromSxTriggered event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.
old-location: wdf\evtdevicewakefromsxtriggered.htm
tech.root: wdf
ms.assetid: a1899d90-4906-458d-b7e3-122655f4d926
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_38946496-1155-44d9-8636-8343c4623000.xml, EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED, EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED callback, EvtDeviceWakeFromSxTriggered, EvtDeviceWakeFromSxTriggered callback function, kmdf.evtdevicewakefromsxtriggered, wdf.evtdevicewakefromsxtriggered, wdfdevice/EvtDeviceWakeFromSxTriggered
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceWakeFromSxTriggered"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceWakeFromSxTriggered
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceWakeFromSxTriggered</i> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



None




## -remarks



To register an <i>EvtDeviceWakeFromSxTriggered</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered this callback, the framework calls it after calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function and before calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <i>EvtDeviceWakeFromSxTriggered</i> callback function will not be called even though the driver's device triggered a wake signal.

Some buses combine wake signals from several children. If your device is connected to one of these buses, the callback function might have to determine if the current device triggered the wake-up signal. If your device provides a hardware latch that saves the device's triggered state, it is best to check that state in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a> callback function, because that callback is always called after the device wakes up, even if the wake signal was dropped.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.


#### Examples

To define an <i>EvtDeviceWakeFromSxTriggered</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWakeFromSxTriggered</i> callback function that is named <i>MyDeviceWakeFromSxTriggered</i>, use the <b>EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED  MyDeviceWakeFromSxTriggered;</pre>
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
 MyDeviceWakeFromSxTriggered (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_WAKE_FROM_SX_TRIGGERED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx">EvtDeviceDisarmWakeFromSx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered">EvtDeviceWakeFromS0Triggered</a>
 

 

