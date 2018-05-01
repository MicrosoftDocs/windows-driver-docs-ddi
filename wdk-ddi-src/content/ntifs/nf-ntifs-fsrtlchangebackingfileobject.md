---
UID: NF:ntifs.FsRtlChangeBackingFileObject
title: FsRtlChangeBackingFileObject function
author: windows-driver-content
description: The FsRtlChangeBackingFileObject routine replaces the current file object with a new file object.
old-location: ifsk\fsrtlchangebackingfileobject.htm
old-project: ifsk
ms.assetid: a3ef4644-8e17-4f67-ba7f-61d62c534c26
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlChangeBackingFileObject, FsRtlChangeBackingFileObject routine [Installable File System Drivers], fsrtlref_4dd83ba3-8d9b-4c5b-a4ea-d7a0ceaaa9f2.xml, ifsk.fsrtlchangebackingfileobject, ntifs/FsRtlChangeBackingFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlChangeBackingFileObject routine is available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlChangeBackingFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# FsRtlChangeBackingFileObject function


## -description


The <b>FsRtlChangeBackingFileObject</b> routine replaces the current file object with a new file object.


## -parameters




### -param CurrentFileObject [in, optional]

The current file object. If this object does not belong to the stream, the operation fails.


### -param NewFileObject [in]

The new file object.


### -param ChangeBackingType [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff547341">FSRTL_CHANGE_BACKING_TYPE</a> enumeration value that indicates which internal memory area the new file object will designate.


### -param Flags [in]

Reserved for future use.


## -returns



The <b>FsRtlChangeBackingFileObject</b> routine returns STATUS_SUCCESS if the operation succeeds. Otherwise, <b>FsRtlChangeBackingFileObject</b> returns the appropriate error code.The following table contains error codes that <b>FsRtlChangeBackingFileObject</b> might return.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The change operation failed because the file object that <i>NewFileObject</i> specifies does not represent the same stream as <i>CurrentFileObject</i>.  

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The change operation failed because the caller specified an invalid backing type in <i>ChangeBackingType</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The change operation failed because the caller specified an invalid value in <i>Flags</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORT</b></dt>
</dl>
</td>
<td width="60%">
The change operation failed because the caller obtained the file object in a way that does not allow subsequent swapping of the file object. For example, if the caller obtained the file object with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539104">CcGetFileObjectFromSectionPtrs</a>, it is not safe to swap the file object.

</td>
</tr>
</table>
 




## -remarks



The <b>FsRtlChangeBackingFileObject</b> routine changes the file object for one of the following:

<ul>
<li>
One of the memory manager's image control areas for the stream

</li>
<li>
The memory manager's data control area for the stream

</li>
<li>
The cache manager's shared cache map for the stream

</li>
</ul>
The <b>FsRtlChangeBackingFileObject</b> routine is not synchronous. It processes the request for a change of file object and returns immediately. The cache manager and the memory manager synchronize the change of the file object and will not free the old file object until all incomplete operations that are associated with the old file object have finished. A return status of STATUS_SUCCESS from <b>FsRtlChangeBackingFileObject</b> does not mean that the operating system has already changed the file object.

However, after <b>FsRtlChangeBackingFileObject</b> runs successfully, the operating system associates all future operations with the new file object.

To change the file object for more than one backing type, the caller must call <b>FsRtlChangeBackingFileObject</b> multiple times, one time for each backing type to change.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547341">FSRTL_CHANGE_BACKING_TYPE</a>
 

 

