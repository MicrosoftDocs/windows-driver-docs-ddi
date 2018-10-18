---
UID: NF:wdfdevice.WdfDeviceGetDevicePowerPolicyState
title: WdfDeviceGetDevicePowerPolicyState function
author: windows-driver-content
description: The WdfDeviceGetDevicePowerPolicyState method returns the current state of the framework's power policy state machine, for a specified device.
old-location: wdf\wdfdevicegetdevicepowerpolicystate.htm
tech.root: wdf
ms.assetid: 3a4aab60-6568-4017-acad-ca643cb4d661
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_34dd5376-7889-4900-bcd9-65ad9ff732e2.xml, WdfDeviceGetDevicePowerPolicyState, WdfDeviceGetDevicePowerPolicyState method, kmdf.wdfdevicegetdevicepowerpolicystate, wdf.wdfdevicegetdevicepowerpolicystate, wdfdevice/WdfDeviceGetDevicePowerPolicyState
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
-	WdfDeviceGetDevicePowerPolicyState
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceGetDevicePowerPolicyState function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns the current state of the framework's power policy state machine, for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



<b>WdfDeviceGetDevicePowerPolicyState</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551275">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator that identifies the current state of the framework's power policy state machine for the specified device. 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Most drivers do not need to be aware of the state of the framework's power policy state machine. For more information about the framework's state machines, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.

The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns a meaningful value only if it is called from within the callback functions that the driver registers when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.


#### Examples

The following code example obtains the current state of the framework's power policy state machine for a specified device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_POLICY_STATE devicePowerPolicyState;

devicePowerPolicyState = WdfDeviceGetDevicePowerPolicyState(Device);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546966">WdfDevStateNormalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545969">WdfDeviceGetDevicePnpState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545985">WdfDeviceGetDevicePowerState</a>
 

 

