---
UID: NF:ntifs.IoReplaceFileObjectName
title: IoReplaceFileObjectName function (ntifs.h)
description: The IoReplaceFileObjectName routine replaces the name of a file object.
old-location: ifsk\ioreplacefileobjectname.htm
tech.root: ifsk
ms.assetid: 1550a35f-2733-4ee8-9715-d82f96eb5da7
ms.date: 04/16/2018
ms.keywords: IoReplaceFileObjectName, IoReplaceFileObjectName routine [Installable File System Drivers], ifsk.ioreplacefileobjectname, ioref_3e18058f-46a0-4345-9d67-2e211bbb84a8.xml, ntifs/IoReplaceFileObjectName
ms.topic: function
f1_keywords:
 - "ntifs/IoReplaceFileObjectName"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoReplaceFileObjectName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoReplaceFileObjectName function


## -description


The <b>IoReplaceFileObjectName</b> routine replaces the name of a file object.


## -parameters




### -param FileObject [in]

Pointer to the file object whose file name is being replaced. 


### -param NewFileName [in]

Pointer to the string buffer for the new name for the file object.


### -param FileNameLength [in]

Length, in bytes, of the new name for the file object. 


## -returns



Returns STATUS_SUCCESS or one of the following NTSTATUS values otherwise:

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
Indicates that the file object provided does not have a name to replace.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that inadequate memory is available to allocate a buffer to complete this operation.

</td>
</tr>
</table>
 




## -remarks



Drivers should use <b>IoReplaceFileObjectName</b> to safely replace the name in a file object. This allows the I/O manager to control the lifetime of the buffer associated with the file object. Replacing a file object name directly without using <b>IoReplaceFileObjectName</b> may conflict with other uses of the name and should be avoided when possible.

This routine should be used to replace the file object name instead of doing so manually to allow the kernel to manage the lifetime of the name correctly.



