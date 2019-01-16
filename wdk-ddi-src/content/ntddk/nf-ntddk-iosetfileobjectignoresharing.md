---
UID: NF:ntddk.IoSetFileObjectIgnoreSharing
title: IoSetFileObjectIgnoreSharing function
description: The IoSetFileObjectIgnoreSharing routine sets a file object to ignore file sharing access checks.
old-location: ifsk\iosetfileobjectignoresharing.htm
tech.root: ifsk
ms.assetid: 14863379-0639-4D24-AFA4-AE2196328B87
ms.date: 04/16/2018
ms.keywords: IoSetFileObjectIgnoreSharing, IoSetFileObjectIgnoreSharing routine [Installable File System Drivers], ifsk.iosetfileobjectignoresharing, ntddk/IoSetFileObjectIgnoreSharing
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows 7.
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
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetFileObjectIgnoreSharing
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetFileObjectIgnoreSharing function


## -description


The <b>IoSetFileObjectIgnoreSharing</b> routine sets a file object to ignore file  sharing access checks.


## -parameters




### -param FileObject

Pointer to a file object for the file.


## -returns



<b>IoSetFileObjectIgnoreSharing</b> returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The option information for <i>FileObject</i> was not found. The status of sharing access checking cannot be set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The option information was not created for <i>FileObject</i>. The status of sharing access checking cannot be set.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj126226">IoIsFileObjectIgnoringSharing</a>
 

 

