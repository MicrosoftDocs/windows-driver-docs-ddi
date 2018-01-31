---
UID: NF:ntifs.PsIsThreadTerminating
title: PsIsThreadTerminating function
author: windows-driver-content
description: The PsIsThreadTerminating routine checks whether a thread is terminating.
old-location: ifsk\psisthreadterminating.htm
old-project: ifsk
ms.assetid: 2b82b060-79ea-4add-b559-af37c954537e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.psisthreadterminating, ntifs/PsIsThreadTerminating, PsIsThreadTerminating, PsIsThreadTerminating routine [Installable File System Drivers], psref_55824a18-3df1-4d43-bc9c-77da8ee6cf6c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsIsThreadTerminating
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsIsThreadTerminating function


## -description


The <b>PsIsThreadTerminating</b> routine checks whether a thread is terminating.


## -syntax


````
BOOLEAN PsIsThreadTerminating(
  _In_ PETHREAD Thread
);
````


## -parameters




#### - Thread [in]

A pointer to the thread to be checked for termination.


## -returns


The <b>PsIsThreadTerminating</b> routine returns <b>TRUE</b> if the thread is terminating, otherwise <b>FALSE</b>.



## -remarks


For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-psgetprocessexittime.md">PsGetProcessExitTime</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsIsThreadTerminating routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

