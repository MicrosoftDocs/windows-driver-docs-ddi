---
UID: NF:wdfdevice.WdfDeviceGetDevicePowerState
title: WdfDeviceGetDevicePowerState function
author: windows-driver-content
description: The WdfDeviceGetDevicePowerState method returns the current state of the framework's power state machine, for a specified device.
old-location: wdf\wdfdevicegetdevicepowerstate.htm
old-project: wdf
ms.assetid: 7405e0c7-9263-4911-9b1e-52cffa559af3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_40013978-2c8d-4776-b218-5f0c743e57e9.xml, WdfDeviceGetDevicePowerState, WdfDeviceGetDevicePowerState method, kmdf.wdfdevicegetdevicepowerstate, wdf.wdfdevicegetdevicepowerstate, wdfdevice/WdfDeviceGetDevicePowerState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceGetDevicePowerState
product: Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceGetDevicePowerState function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetDevicePowerState</b> method returns the current state of the framework's power state machine, for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



<b>WdfDeviceGetDevicePowerState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551280">WDF_DEVICE_POWER_STATE</a>-typed enumerator that identifies the current state of the framework's power state machine for the specified device. 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Most drivers do not need to be aware of the state of the framework's power state machine. For more information about the framework's state machines, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

The <b>WdfDeviceGetDevicePowerState</b> method returns a meaningful value only if it is called from within the following callback functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a>


</li>
<li>

<a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>


</li>
<li>

<a href="https://msdn.microsoft.com/38d74ce1-9d9d-4da5-a2b3-579048850b28">EvtDeviceD0EntryPostInterruptsEnabled</a>


</li>
<li>

<a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a>


</li>
<li>

<a href="https://msdn.microsoft.com/8f57c3b3-2dcf-44a3-a3c2-c9585bdfa253">EvtDeviceD0ExitPreInterruptsDisabled</a>


</li>
<li>

<a href="https://msdn.microsoft.com/9dbc66db-ea94-4e6a-9618-00999a9dd641">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="https://msdn.microsoft.com/85a569ea-eb14-4453-9591-fc44afbd3a59">EvtDeviceSelfManagedIoSuspend</a>


</li>
<li>

<a href="https://msdn.microsoft.com/13d7fbc6-6f93-4ef9-abd4-f2adc4e8e23a">EvtDeviceSelfManagedIoRestart</a>


</li>
</ul>

#### Examples

The following code example obtains the current state of the framework's power state machine for a specified device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_STATE state;

state = WdfDeviceGetDevicePowerState(Device);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546966">WdfDevStateNormalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545969">WdfDeviceGetDevicePnpState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545974">WdfDeviceGetDevicePowerPolicyState</a>
 

 

