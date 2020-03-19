---
UID: NF:ntifs.PsIsThreadTerminating
title: PsIsThreadTerminating function (ntifs.h)
description: The PsIsThreadTerminating routine checks whether a thread is terminating.
old-location: ifsk\psisthreadterminating.htm
tech.root: ifsk
ms.assetid: 2b82b060-79ea-4add-b559-af37c954537e
ms.date: 04/16/2018
keywords: ["PsIsThreadTerminating function"]
ms.keywords: PsIsThreadTerminating, PsIsThreadTerminating routine [Installable File System Drivers], ifsk.psisthreadterminating, ntifs/PsIsThreadTerminating, psref_55824a18-3df1-4d43-bc9c-77da8ee6cf6c.xml
f1_keywords:
 - "ntifs/PsIsThreadTerminating"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later Windows operating systems.
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
- PsIsThreadTerminating
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsIsThreadTerminating function


## -description


The <b>PsIsThreadTerminating</b> routine checks whether a thread is terminating.


## -parameters




### -param Thread [in]

A pointer to the thread to be checked for termination.


## -returns



The <b>PsIsThreadTerminating</b> routine returns <b>TRUE</b> if the thread is terminating, otherwise <b>FALSE</b>.




## -remarks



For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psgetprocessexittime">PsGetProcessExitTime</a>
 

 

