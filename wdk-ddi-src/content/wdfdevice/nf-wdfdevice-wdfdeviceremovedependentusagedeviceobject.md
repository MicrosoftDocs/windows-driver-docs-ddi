---
UID: NF:wdfdevice.WdfDeviceRemoveDependentUsageDeviceObject
title: WdfDeviceRemoveDependentUsageDeviceObject function
author: windows-driver-content
description: The WdfDeviceRemoveDependentUsageDeviceObject method indicates that a specified device no longer depends on another device when the specified device is used to store special files.
old-location: wdf\wdfdeviceremovedependentusagedeviceobject.htm
old-project: wdf
ms.assetid: d9569b4b-ad71-46dd-b421-8493f595f030
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_22cf19f5-c56f-430f-a6a1-d15af92eb41b.xml, WdfDeviceRemoveDependentUsageDeviceObject, WdfDeviceRemoveDependentUsageDeviceObject method, kmdf.wdfdeviceremovedependentusagedeviceobject, wdf.wdfdeviceremovedependentusagedeviceobject, wdfdevice/WdfDeviceRemoveDependentUsageDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceRemoveDependentUsageDeviceObject
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceRemoveDependentUsageDeviceObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceRemoveDependentUsageDeviceObject</b> method indicates that a specified device no longer depends on another device when the specified device is used to store <a href="https://msdn.microsoft.com/3879570f-e083-4eaf-aa5b-9b78d8f826c1">special files</a>. 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DependentDevice [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that identifies a device that <i>Device</i> depends on.


## -returns



None.




## -remarks



Your driver can call <b>WdfDeviceRemoveDependentUsageDeviceObject</b> to remove a device dependency that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545864">WdfDeviceAddDependentUsageDeviceObject</a> created.

For more information about <b>WdfDeviceRemoveDependentUsageDeviceObject</b> and <b>WdfDeviceRemoveDependentUsageDeviceObject</b>, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>. 


#### Examples

The following code example removes a device (<b>pDeviceObject</b>) from the list of devices that another device (<b>device</b>) depends on.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfDeviceRemoveDependentUsageDeviceObject(
                                                device,
                                                pDeviceObject
                                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545864">WdfDeviceAddDependentUsageDeviceObject</a>
 

 

