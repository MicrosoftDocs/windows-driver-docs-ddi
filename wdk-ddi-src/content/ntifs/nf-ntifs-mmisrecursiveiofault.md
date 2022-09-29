---
UID: NF:ntifs.MmIsRecursiveIoFault
title: MmIsRecursiveIoFault function (ntifs.h)
description: The MmIsRecursiveIoFault routine determines whether the current page fault is occurring during an I/O operation.
old-location: ifsk\mmisrecursiveiofault.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["MmIsRecursiveIoFault function"]
ms.keywords: MmIsRecursiveIoFault, MmIsRecursiveIoFault routine [Installable File System Drivers], ifsk.mmisrecursiveiofault, mmref_2f97ee70-0e70-4607-841e-e9d5b3ae74c8.xml, ntifs/MmIsRecursiveIoFault
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmIsRecursiveIoFault
 - ntifs/MmIsRecursiveIoFault
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmIsRecursiveIoFault
---

# MmIsRecursiveIoFault function


## -description

The <b>MmIsRecursiveIoFault</b> routine determines whether the current page fault is occurring during an I/O operation.

## -returns

<b>MmIsRecursiveIoFault</b> returns <b>TRUE</b> if a file system I/O operation is in progress for the current thread, <b>FALSE</b> otherwise.

## -remarks

When a page fault occurs, the file system can call <b>MmIsRecursiveIoFault</b> to determine whether an I/O operation is in progress for the current thread.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmisaddressvalid">MmIsAddressValid</a>
