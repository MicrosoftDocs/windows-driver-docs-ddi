---
UID: NF:ntifs.MmIsRecursiveIoFault
title: MmIsRecursiveIoFault function (ntifs.h)
description: The MmIsRecursiveIoFault routine determines whether the current page fault is occurring during an I/O operation.
old-location: ifsk\mmisrecursiveiofault.htm
tech.root: ifsk
ms.assetid: c445c016-2781-4a82-ac2d-4c6eaff3b4c8
ms.date: 04/16/2018
keywords: ["MmIsRecursiveIoFault function"]
ms.keywords: MmIsRecursiveIoFault, MmIsRecursiveIoFault routine [Installable File System Drivers], ifsk.mmisrecursiveiofault, mmref_2f97ee70-0e70-4607-841e-e9d5b3ae74c8.xml, ntifs/MmIsRecursiveIoFault
f1_keywords:
 - "ntifs/MmIsRecursiveIoFault"
 - "MmIsRecursiveIoFault"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmIsRecursiveIoFault
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmIsRecursiveIoFault function


## -description


The <b>MmIsRecursiveIoFault</b> routine determines whether the current page fault is occurring during an I/O operation.


## -returns



<b>MmIsRecursiveIoFault</b> returns <b>TRUE</b> if a file system I/O operation is in progress for the current thread, <b>FALSE</b> otherwise.




## -remarks



When a page fault occurs, the file system can call <b>MmIsRecursiveIoFault</b> to determine whether an I/O operation is in progress for the current thread.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmisaddressvalid">MmIsAddressValid</a>
 

 

