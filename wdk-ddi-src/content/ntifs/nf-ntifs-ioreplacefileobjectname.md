---
UID: NF:ntifs.IoReplaceFileObjectName
title: IoReplaceFileObjectName function
author: windows-driver-content
description: The IoReplaceFileObjectName routine replaces the name of a file object.
old-location: ifsk\ioreplacefileobjectname.htm
old-project: ifsk
ms.assetid: 1550a35f-2733-4ee8-9715-d82f96eb5da7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoReplaceFileObjectName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoReplaceFileObjectName
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# IoReplaceFileObjectName function



## -description
The <b>IoReplaceFileObjectName</b> routine replaces the name of a file object.



## -syntax

````
NTSTATUS IoReplaceFileObjectName(
  _In_ PFILE_OBJECT FileObject,
  _In_ PWSTR        NewFileName,
  _In_ USHORT       FileNameLength
);
````


## -parameters

### -param FileObject [in]

Pointer to the file object whose file name is being replaced. 


### -param NewFileName [in]

Pointer to the string buffer for the new name for the file object.


### -param FileNameLength [in]

Length, in bytes, of the new name for the file object. 


## -returns
Returns STATUS_SUCCESS or one of the following NTSTATUS values otherwise:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Indicates that the file object provided does not have a name to replace.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Indicates that inadequate memory is available to allocate a buffer to complete this operation.

 


## -remarks
Drivers should use <b>IoReplaceFileObjectName</b> to safely replace the name in a file object. This allows the I/O manager to control the lifetime of the buffer associated with the file object. Replacing a file object name directly without using <b>IoReplaceFileObjectName</b> may conflict with other uses of the name and should be avoided when possible.

This routine should be used to replace the file object name instead of doing so manually to allow the kernel to manage the lifetime of the name correctly.</p>