---
UID: NC:wdfpdo.EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS
title: EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS (wdfpdo.h)
description: A bus driver's EvtDeviceEnableWakeAtBus event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus.
old-location: wdf\evtdeviceenablewakeatbus.htm
tech.root: wdf
ms.assetid: 902c9bdc-d83a-4bc2-802c-1aaba43c9e2e
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_c418526b-2cf2-4193-b75c-f6af5d669433.xml, EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS, EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback, EvtDeviceEnableWakeAtBus, EvtDeviceEnableWakeAtBus callback function, kmdf.evtdeviceenablewakeatbus, wdf.evtdeviceenablewakeatbus, wdfpdo/EvtDeviceEnableWakeAtBus
ms.topic: callback
f1_keywords:
 - "wdfpdo/EvtDeviceEnableWakeAtBus"
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
- EvtDeviceEnableWakeAtBus
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A bus driver's <i>EvtDeviceEnableWakeAtBus</i> event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PowerState [in]

A SYSTEM_POWER_STATE-typed enumerator that identifies the system power state that the system or device will wake from.


## -returns



If the <i>EvtDeviceEnableWakeAtBus</i> callback function encountered no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_disable_wake_at_bus">EvtDeviceDisableWakeAtBus</a> callback function.

 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.






## -remarks



For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.


#### Examples

To define an <i>EvtDeviceEnableWakeAtBus</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceEnableWakeAtBus</i> callback function that is named <i>MyDeviceEnableWakeAtBus</i>, use the <b>EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS  MyDeviceEnableWakeAtBus;</pre>
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
 MyDeviceEnableWakeAtBus (
    WDFDEVICE  Device,
    SYSTEM_POWER_STATE  PowerState
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nc-wdfpdo-evt_wdf_device_disable_wake_at_bus">EvtDeviceDisableWakeAtBus</a>
 

 

