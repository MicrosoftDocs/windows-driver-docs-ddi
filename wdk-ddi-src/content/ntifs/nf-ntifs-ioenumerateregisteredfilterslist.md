---
UID: NF:ntifs.IoEnumerateRegisteredFiltersList
title: IoEnumerateRegisteredFiltersList function
author: windows-driver-content
description: The IoEnumerateRegisteredFiltersList routine enumerates the file system filter drivers that have registered with the system.
old-location: ifsk\ioenumerateregisteredfilterslist.htm
tech.root: ifsk
ms.assetid: 7ac67110-bc92-457a-88f4-a21f2fa38174
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IoEnumerateRegisteredFiltersList, IoEnumerateRegisteredFiltersList routine [Installable File System Drivers], ifsk.ioenumerateregisteredfilterslist, ioref_b1530889-7d8a-4fd7-a7d3-954b1c7012ca.xml, ntifs/IoEnumerateRegisteredFiltersList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows Server 2003 Service Pack 1 (SP1) and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoEnumerateRegisteredFiltersList
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoEnumerateRegisteredFiltersList function


## -description


The <b>IoEnumerateRegisteredFiltersList</b> routine enumerates the file system filter drivers that have registered with the system. 


## -parameters




### -param DriverObjectList [out]

A pointer to a caller-allocated array that receives the driver object pointers. This parameter is optional and can be <b>NULL</b>. (See the following Remarks section.) 


### -param DriverObjectListSize [in]

Size, in bytes, of the <i>DriverObjectList</i> array. Can be zero. (See the following Remarks section.) 


### -param ActualNumberDriverObjects [out]

Actual number of driver objects found. Note that if the array at <i>DriverObjectList</i> is too small, the number of driver object pointers that are copied into the array will be less than <i>ActualNumberDriverObjects</i>. 


## -returns



<b>IoEnumerateRegisteredFiltersList</b> can return one of the following: 

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
The call to <b>IoEnumerateRegisteredFiltersList</b> was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The array at <i>DriverObjectList</i> is too small to hold the entire driver object list. In this case, <b>IoEnumerateRegisteredFiltersList</b> copies as many driver object pointers into the array as possible. 

</td>
</tr>
</table>
 




## -remarks



A file system filter driver calls <b>IoEnumerateRegisteredFiltersList</b> to obtain an array of pointers to the driver objects for all file system filter drivers that have called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>. 

The filter drivers are enumerated in order of decreasing distance from the base file system. The first element (index zero) in the <i>DriverObjectList</i> array represents the filter that is attached farthest from the file system. The second entry is for the next-farthest filter, and so on. The last entry in the array is for the filter that is closest to the base file system. 

<b>IoEnumerateRegisteredFiltersList</b> enumerates only file system filter drivers (also called "legacy filters"). It does not enumerate minifilters. To enumerate both minifilters and legacy filters, or only minifilters, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>. 

The filter driver typically calls <b>IoEnumerateRegisteredFiltersList</b> twice: once to get the number of driver objects in the list, and once to get the driver object list itself. In the first call, the caller should set the <i>DriverObjectList</i> parameter to <b>NULL</b> and <i>DriverObjectListSize</i> to zero. In the second call, <i>DriverObjectList</i> should contain a pointer to an appropriately-sized pointer array, and <i>DriverObjectListSize</i> should contain the size, in bytes, of that array. 

<b>IoEnumerateRegisteredFiltersList</b> increments the reference count on every driver object in the list pointed to by <i>DriverObjectList</i>. Thus every successful call to <b>IoEnumerateRegisteredFiltersList</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>for each driver object in the list. Failure to do so prevents the system from freeing or deleting these driver objects because of an outstanding reference count. 

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a> instead of <b>IoEnumerateRegisteredFiltersList</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542060">FltEnumerateFilterInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542064">FltEnumerateFilters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
 

 

