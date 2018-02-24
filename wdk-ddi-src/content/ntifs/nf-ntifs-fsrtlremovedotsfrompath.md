---
UID: NF:ntifs.FsRtlRemoveDotsFromPath
title: FsRtlRemoveDotsFromPath function
author: windows-driver-content
description: The FsRtlRemoveDotsFromPath routine removes unnecessary occurrences of '.' and '..' from the specified path.
old-location: ifsk\fsrtlremovedotsfrompath.htm
old-project: ifsk
ms.assetid: af6ecdb7-8713-460d-8fd9-ef027ac15b39
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlRemoveDotsFromPath, fsrtlref_93b15313-3292-4122-9852-731b995e9d20.xml, ntifs/FsRtlRemoveDotsFromPath, ifsk.fsrtlremovedotsfrompath, FsRtlRemoveDotsFromPath routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlRemoveDotsFromPath
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlRemoveDotsFromPath function


## -description


The <b>FsRtlRemoveDotsFromPath</b> routine removes unnecessary occurrences of '.' and '..' from the specified path.


## -syntax


````
NTSTATUS FsRtlRemoveDotsFromPath(
  _Inout_ PWSTR  OriginalString,
  _In_    USHORT PathLength,
  _Out_   USHORT *NewLength
);
````


## -parameters




### -param OriginalString [in, out]

A pointer to the buffer to be processed.


### -param PathLength [in]

The length of buffer (in bytes).


### -param NewLength [out]

A pointer to the new length of the buffer, after processing.


## -returns



The<b> FsRtlRemoveDotsFromPath</b> routine returns either STATUS_SUCCESS value for success or STATUS_IO_REPARSE_DATA_INVALID if the operation could not be completed.




## -remarks



This routine would take a path as <i>OriginalString</i> like the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\dir1\dir2\..\dir3\.\file.txt</pre>
</td>
</tr>
</table></span></div>
The routine would modify <i>OriginalString</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\dir1\dir3\file.txt</pre>
</td>
</tr>
</table></span></div>
The routine will fail with STATUS_IO_REPARSE_DATA_INVALID if any of the following strings are passed as <i>OriginalString</i>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\..
..
..\anyOtherContent</pre>
</td>
</tr>
</table></span></div>


