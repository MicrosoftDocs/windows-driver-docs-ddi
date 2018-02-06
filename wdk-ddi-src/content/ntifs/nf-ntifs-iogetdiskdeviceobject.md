---
UID: NF:ntifs.IoGetDiskDeviceObject
title: IoGetDiskDeviceObject function
author: windows-driver-content
description: The IoGetDiskDeviceObject routine retrieves a pointer to the disk device object associated with a given file system volume device object.
old-location: ifsk\iogetdiskdeviceobject.htm
old-project: ifsk
ms.assetid: c4f27011-f198-474e-8d2c-8bf35c3c8c66
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.iogetdiskdeviceobject, IoGetDiskDeviceObject routine [Installable File System Drivers], IoGetDiskDeviceObject, ntifs/IoGetDiskDeviceObject, ioref_b3532bdd-87b6-4e6b-91a0-093b8ed5aa6c.xml
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
-	IoGetDiskDeviceObject
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetDiskDeviceObject function


## -description


The <b>IoGetDiskDeviceObject</b> routine retrieves a pointer to the disk device object associated with a given file system volume device object.


## -syntax


````
NTSTATUS IoGetDiskDeviceObject(
  _In_  PDEVICE_OBJECT FileSystemDeviceObject,
  _Out_ PDEVICE_OBJECT *DeviceObject
);
````


## -parameters




### -param FileSystemDeviceObject [in]

A pointer to the file system device object. 


### -param DiskDeviceObject

TBD



#### - DeviceObject [out]

A pointer to a variable that receives the address of the device object for the disk device object. 


## -returns


<b>IoGetDiskDeviceObject</b> returns one of the following status values: 
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
One of the parameters passed to this function was invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
</table> 



## -remarks


<b>IoGetDiskDeviceObject</b> returns a pointer to the storage device object associated with the file system volume. The storage device need not be an actual disk 

File system filter drivers typically call <b>IoGetDiskDeviceObject</b> for a file system volume device object to determine whether the volume is mounted. 

<b>IoGetDiskDeviceObject</b> increments the reference count on the disk device object pointed to by <i>DeviceObject</i>. Thus every successful call to <b>IoGetDiskDeviceObject</b> must be matched by a subsequent call to <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-ioenumeratedeviceobjectlist.md">IoEnumerateDeviceObjectList</a>

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>

<a href="..\ntifs\nf-ntifs-iogetattacheddevice.md">IoGetAttachedDevice</a>

<a href="..\ntifs\nf-ntifs-iogetattacheddevicereference.md">IoGetAttachedDeviceReference</a>

<a href="..\ntifs\nf-ntifs-iogetlowerdeviceobject.md">IoGetLowerDeviceObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetDiskDeviceObject routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

