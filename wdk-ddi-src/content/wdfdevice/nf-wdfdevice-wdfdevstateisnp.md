---
UID: NF:wdfdevice.WdfDevStateIsNP
title: WdfDevStateIsNP function
author: windows-driver-content
description: The WdfDevStateIsNP method returns a Boolean value that indicates whether a specified power state or power policy state is a nonpageable state.
old-location: wdf\wdfdevstateisnp.htm
old-project: wdf
ms.assetid: 49584600-e470-4be8-9111-3e890a9fedfd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_ed6dd7ac-b5e3-49b2-a4d8-08e4e9377321.xml, WdfDevStateIsNP, WdfDevStateIsNP method, kmdf.wdfdevstateisnp, wdf.wdfdevstateisnp, wdfdevice/WdfDevStateIsNP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDevStateIsNP
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDevStateIsNP function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDevStateIsNP</b> method returns a Boolean value that indicates whether a specified power state or power policy state is a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">nonpageable</a> state. 


## -syntax


````
BOOLEAN WdfDevStateIsNP(
  _In_ ULONG State
);
````


## -parameters




### -param State [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_power_state.md">WDF_DEVICE_POWER_STATE</a>-typed enumerator or a <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_power_policy_state.md">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator.


## -returns



If the calling driver is currently nonpageable, the <b>WdfDevStateIsNP</b> method returns <b>TRUE</b>. Otherwise, the method returns <b>FALSE</b>.




## -remarks



To obtain the current state of the framework's power state machine, a driver can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerstate.md">WdfDeviceGetDevicePowerState</a> from within a PnP or power callback function. To obtain the current state of the framework's power policy state machine, a driver can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md">WdfDeviceGetDevicePowerPolicyState</a> from within a power policy callback function. After the driver has called <b>WdfDeviceGetDevicePowerState</b> or <b>WdfDeviceGetDevicePowerPolicyState</b>, it can call <b>WdfDevStateIsNP</b> to determine if the returned state represents a pageable or nonpageable state. If the framework's state machine is in a nonpageable state, the driver is not pageable and must not perform any operations that might cause the operating system to access the paging file. Such operations include accessing files, the registry, or paged pool. 


#### Examples

The following code example sets the <b>nonpageable</b> value to <b>TRUE</b> if the framework's power state machine is currently in a nonpageable state.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN nonpageable;

nonpageable = WdfDevStateIsNP(WdfDeviceGetDevicePowerState(device));</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpageable.md">WdfDeviceInitSetPowerPageable</a>



 

 


