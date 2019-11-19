---
UID: NC:wdfpdo.EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS
title: EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS (wdfpdo.h)
description: A bus driver's EvtDeviceDisableWakeAtBus event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.
old-location: wdf\evtdevicedisablewakeatbus.htm
tech.root: wdf
ms.assetid: 91ae9694-5020-42ee-b882-a753e9bbe919
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_3f6a4a69-a6aa-48a5-9a6a-fd64c569edca.xml, EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS, EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback, EvtDeviceDisableWakeAtBus, EvtDeviceDisableWakeAtBus callback function, kmdf.evtdevicedisablewakeatbus, wdf.evtdevicedisablewakeatbus, wdfpdo/EvtDeviceDisableWakeAtBus
ms.topic: callback
f1_keywords:
 - "wdfpdo/EvtDeviceDisableWakeAtBus"
req.header: wdfpdo.h
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
- Wdfpdo.h
api_name:
- EvtDeviceDisableWakeAtBus
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceDisableWakeAtBus</i> event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks



For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.


#### Examples

To define an <i>EvtDeviceDisableWakeAtBus</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceDisableWakeAtBus</i> callback function that is named <i>MyDeviceDisableWakeAtBus</i>, use the <b>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS  MyDeviceDisableWakeAtBus;</pre>
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
 MyDeviceDisableWakeAtBus (
    WDFDEVICE  Device
    )
  {...} </pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_enable_wake_at_bus">EvtDeviceEnableWakeAtBus</a>
 

 

