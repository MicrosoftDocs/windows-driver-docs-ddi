---
UID: NF:ntifs.PsIsThreadTerminating
title: PsIsThreadTerminating function
author: windows-driver-content
description: The PsIsThreadTerminating routine checks whether a thread is terminating.
old-location: ifsk\psisthreadterminating.htm
old-project: ifsk
ms.assetid: 2b82b060-79ea-4add-b559-af37c954537e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsIsThreadTerminating, PsIsThreadTerminating routine [Installable File System Drivers], ifsk.psisthreadterminating, ntifs/PsIsThreadTerminating, psref_55824a18-3df1-4d43-bc9c-77da8ee6cf6c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsIsThreadTerminating
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
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



For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551902">PsGetProcessExitTime</a>
 

 

