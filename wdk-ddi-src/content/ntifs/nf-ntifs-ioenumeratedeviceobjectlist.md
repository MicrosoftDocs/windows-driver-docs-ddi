---
UID: NF:ntifs.IoEnumerateDeviceObjectList
title: IoEnumerateDeviceObjectList function
author: windows-driver-content
description: The IoEnumerateDeviceObjectList routine enumerates a driver's device object list.
old-location: ifsk\ioenumeratedeviceobjectlist.htm
old-project: ifsk
ms.assetid: ce6cec58-2122-49c3-8c5c-172df2c4dd04
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: IoEnumerateDeviceObjectList routine [Installable File System Drivers], IoEnumerateDeviceObjectList, ifsk.ioenumeratedeviceobjectlist, ioref_5bfd9f2c-73c0-4f69-8a5e-4cc105c2f92a.xml, ntifs/IoEnumerateDeviceObjectList
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoEnumerateDeviceObjectList
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoEnumerateDeviceObjectList function


## -description


The <b>IoEnumerateDeviceObjectList</b> routine enumerates a driver's device object list. 


## -syntax


````
NTSTATUS IoEnumerateDeviceObjectList(
  _In_  PDRIVER_OBJECT DriverObject,
  _Out_ PDEVICE_OBJECT *DeviceObjectList,
  _In_  ULONG          DeviceObjectListSize,
  _Out_ PULONG         ActualNumberDeviceObjects
);
````


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
The device objects it has created. This is commonly done when the driver is preparing to unload. Note that a file system filter driver cannot safely be unloaded from a running system. For more information, see <a href="..\wdm\nf-wdm-zwunloaddriver.md">ZwUnloadDriver</a>.

</li>
<li>
The device objects created by the base file system, so the filter knows the number of volumes to which it can attach.

</li>
</ul>
<b>IoEnumerateDeviceObjectList</b> returns all device objects created by the driver. This includes control device objects (CDO) as well as volume device objects (VDO). The two types of device objects can be distinguished by the fact that, by convention, CDOs are named and VDOs are not. 

In the latter case, the filter driver typically calls <b>IoEnumerateDeviceObjectList</b> twice: once to get the number of device objects in the list, and once to get the device object list itself. In the first call, the caller should set the <i>DeviceObjectList</i> parameter to <b>NULL</b> and <i>DeviceObjectListSize</i> to zero. In the second call, <i>DeviceObjectList</i> should contain a pointer to an appropriately-sized pointer array, and <i>DeviceObjectListSize</i> should contain the size, in bytes, of that array. 

<b>IoEnumerateDeviceObjectList</b> increments the reference count on every device object in the list pointed to by <i>DeviceObjectList</i>. Thus every successful call to <b>IoEnumerateDeviceObjectList</b> must be matched by a subsequent call to <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>for each device object in the list. Failure to do so prevents the system from freeing or deleting these device objects because of an outstanding reference count. 




## -see-also

<a href="..\wdm\nf-wdm-zwunloaddriver.md">ZwUnloadDriver</a>



<a href="..\ntifs\nf-ntifs-iogetlowerdeviceobject.md">IoGetLowerDeviceObject</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\ntifs\nf-ntifs-iogetattacheddevice.md">IoGetAttachedDevice</a>



<a href="..\wdm\nf-wdm-iogetattacheddevicereference.md">IoGetAttachedDeviceReference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoEnumerateDeviceObjectList routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

