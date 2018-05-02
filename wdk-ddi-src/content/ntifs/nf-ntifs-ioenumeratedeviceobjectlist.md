---
UID: NF:ntifs.IoEnumerateDeviceObjectList
title: IoEnumerateDeviceObjectList function
author: windows-driver-content
description: The IoEnumerateDeviceObjectList routine enumerates a driver's device object list.
old-location: ifsk\ioenumeratedeviceobjectlist.htm
old-project: ifsk
ms.assetid: ce6cec58-2122-49c3-8c5c-172df2c4dd04
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IoEnumerateDeviceObjectList, IoEnumerateDeviceObjectList routine [Installable File System Drivers], ifsk.ioenumeratedeviceobjectlist, ioref_5bfd9f2c-73c0-4f69-8a5e-4cc105c2f92a.xml, ntifs/IoEnumerateDeviceObjectList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoEnumerateDeviceObjectList
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoEnumerateDeviceObjectList function


## -description


The <b>IoEnumerateDeviceObjectList</b> routine enumerates a driver's device object list. 


## -parameters




### -param DriverObject [in]

A pointer to the driver object for the driver. 


### -param DeviceObjectList [out]

A pointer to a caller-allocated array that receives the device object pointers. This parameter can be <b>NULL</b>. 


### -param DeviceObjectListSize [in]

Size, in bytes, of the <i>DeviceObjectList</i> array. Can be zero. 


### -param ActualNumberDeviceObjects [out]

Actual number of device objects found in the driver object's device object list. Note that if the array at <i>DeviceObjectList</i> is too small, the number of device object pointers that are copied into the array will be less than <i>ActualNumberDeviceObjects</i>. 


## -returns



<b>IoEnumerateDeviceObjectList</b> can return one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call to <b>IoEnumerateDeviceObjectList</b> was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The array at <i>DeviceObjectList</i> is too small to hold the entire device object list. In this case, <b>IoEnumerateDeviceObjectList</b> copies as many device object pointers into the array as possible. 

</td>
</tr>
</table>
 




## -remarks



A file system filter driver calls <b>IoEnumerateDeviceObjectList</b> to enumerate: 

<ul>
<li>
The device objects it has created. This is commonly done when the driver is preparing to unload. Note that a file system filter driver cannot safely be unloaded from a running system. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567117">ZwUnloadDriver</a>.

</li>
<li>
The device objects created by the base file system, so the filter knows the number of volumes to which it can attach.

</li>
</ul>
<b>IoEnumerateDeviceObjectList</b> returns all device objects created by the driver. This includes control device objects (CDO) as well as volume device objects (VDO). The two types of device objects can be distinguished by the fact that, by convention, CDOs are named and VDOs are not. 

In the latter case, the filter driver typically calls <b>IoEnumerateDeviceObjectList</b> twice: once to get the number of device objects in the list, and once to get the device object list itself. In the first call, the caller should set the <i>DeviceObjectList</i> parameter to <b>NULL</b> and <i>DeviceObjectListSize</i> to zero. In the second call, <i>DeviceObjectList</i> should contain a pointer to an appropriately-sized pointer array, and <i>DeviceObjectListSize</i> should contain the size, in bytes, of that array. 

<b>IoEnumerateDeviceObjectList</b> increments the reference count on every device object in the list pointed to by <i>DeviceObjectList</i>. Thus every successful call to <b>IoEnumerateDeviceObjectList</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>for each device object in the list. Failure to do so prevents the system from freeing or deleting these device objects because of an outstanding reference count. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548359">IoGetAttachedDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548379">IoGetLowerDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567117">ZwUnloadDriver</a>
 

 

