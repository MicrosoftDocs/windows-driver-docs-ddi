---
UID: NF:wdfdevice.WdfDeviceAddDependentUsageDeviceObject
title: WdfDeviceAddDependentUsageDeviceObject function
author: windows-driver-content
description: The WdfDeviceAddDependentUsageDeviceObject method indicates that a specified device depends on another device when the specified device is used to store special files.
old-location: wdf\wdfdeviceadddependentusagedeviceobject.htm
tech.root: wdf
ms.assetid: 025046e2-ffa1-4210-b4aa-ab3d6b211066
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_b31f8226-abd2-49a0-af66-ace2d05a6f17.xml, WdfDeviceAddDependentUsageDeviceObject, WdfDeviceAddDependentUsageDeviceObject method, kmdf.wdfdeviceadddependentusagedeviceobject, wdf.wdfdeviceadddependentusagedeviceobject, wdfdevice/WdfDeviceAddDependentUsageDeviceObject
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
-	WdfDeviceAddDependentUsageDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceAddDependentUsageDeviceObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceAddDependentUsageDeviceObject</b> method indicates that a specified device depends on another device when the specified device is used to store <a href="https://msdn.microsoft.com/3879570f-e083-4eaf-aa5b-9b78d8f826c1">special files</a>. 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DependentDevice [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that identifies a device that <i>Device</i> depends on.


## -returns



If the operation succeeds, <b>WdfDeviceAddDependentUsageDeviceObject</b> method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>DependentDevice</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation failed.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Your driver can call <b>WdfDeviceAddDependentUsageDeviceObject</b> to indicate that the device identified by <i>Device</i> depends on the device identified by <i>DependentDevice</i>, when <i>Device</i> supports special files. If your driver calls <b>WdfDeviceAddDependentUsageDeviceObject</b>, the framework calls the <a href="https://msdn.microsoft.com/b6b7dd80-fd91-4194-8288-4d703983a798">EvtDeviceUsageNotification</a> callback functions in <i>DependentDevice</i>'s drivers before it calls the <i>EvtDeviceUsageNotification</i> callback functions in <i>Device</i>'s drivers.

Your driver can call <b>WdfDeviceAddDependentUsageDeviceObject</b> multiple times to identify multiple devices that <i>Device</i> depends on to support special files.

After a driver has called <b>WdfDeviceAddDependentUsageDeviceObject</b>, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546829">WdfDeviceRemoveDependentUsageDeviceObject</a> to remove the device identified by <i>DependentDevice</i> from the list of devices that <i>Device</i> depends on.

For more information about special files, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>. 


#### Examples

The following code example adds a device (<b>pDeviceObject</b>) to the list of devices that another device (<b>Device</b>) depends on.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfDeviceAddDependentUsageDeviceObject(
                                                device,
                                                pDeviceObject
                                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b6b7dd80-fd91-4194-8288-4d703983a798">EvtDeviceUsageNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546829">WdfDeviceRemoveDependentUsageDeviceObject</a>
 

 

