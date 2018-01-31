---
UID: NF:ntifs.IoReleaseVpbSpinLock
title: IoReleaseVpbSpinLock function
author: windows-driver-content
description: The IoReleaseVpbSpinLock routine releases the Volume Parameter Block (VPB) spin lock.
old-location: ifsk\ioreleasevpbspinlock.htm
old-project: ifsk
ms.assetid: c0b93f32-4c5c-472c-8c13-3e441f86475f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.ioreleasevpbspinlock, ntifs/IoReleaseVpbSpinLock, ioref_6ccdef5f-9874-4e93-8d91-a05b80d5cecf.xml, IoReleaseVpbSpinLock routine [Installable File System Drivers], IoReleaseVpbSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoReleaseVpbSpinLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoReleaseVpbSpinLock function


## -description


The <b>IoReleaseVpbSpinLock</b> routine releases the Volume Parameter Block (VPB) spin lock. 


## -syntax


````
VOID IoReleaseVpbSpinLock(
  _In_ KIRQL Irql
);
````


## -parameters




#### - Irql [in]

Saved IRQL value returned by <a href="..\ntifs\nf-ntifs-ioacquirevpbspinlock.md">IoAcquireVpbSpinLock</a> when the VPB spin lock was acquired. 


## -returns


None



## -remarks


This routine is the reciprocal to <a href="..\ntifs\nf-ntifs-ioacquirevpbspinlock.md">IoAcquireVpbSpinLock</a>. Every successful call to <b>IoAcquireVpbSpinLock</b> must be matched by a subsequent call to <b>IoReleaseVpbSpinLock</b>. 

Before using <a href="..\ntifs\nf-ntifs-ioacquirevpbspinlock.md">IoAcquireVpbSpinLock</a> and <b>IoReleaseVpbSpinLock</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. 

The holder of the VPB spin lock executes at IRQL DISPATCH_LEVEL after calling <a href="..\ntifs\nf-ntifs-ioacquirevpbspinlock.md">IoAcquireVpbSpinLock</a>. <b>IoReleaseVpbSpinLock</b> restores the caller's original IRQL. 



## -see-also

<a href="..\ntifs\nf-ntifs-ioacquirevpbspinlock.md">IoAcquireVpbSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoReleaseVpbSpinLock routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

