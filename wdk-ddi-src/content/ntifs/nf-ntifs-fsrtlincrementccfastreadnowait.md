---
UID: NF:ntifs.FsRtlIncrementCcFastReadNoWait
title: FsRtlIncrementCcFastReadNoWait function
author: windows-driver-content
description: The FsRtlIncrementCcFastReadNoWait routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadnowait.htm
old-project: ifsk
ms.assetid: 14a1b22a-5d1b-4da6-9610-396fa128ce01
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlIncrementCcFastReadNoWait, FsRtlIncrementCcFastReadNoWait routine [Installable File System Drivers], fsrtlref_f72704ce-84b6-4201-a727-b97fd70accfd.xml, ifsk.fsrtlincrementccfastreadnowait, ntifs/FsRtlIncrementCcFastReadNoWait
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlIncrementCcFastReadNoWait
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIncrementCcFastReadNoWait function


## -description


The <b>FsRtlIncrementCcFastReadNoWait</b> routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters.


## -syntax


````
VOID FsRtlIncrementCcFastReadNoWait(
   VOID 
);
````


## -parameters








## -returns



This routine does not return a value.




## -remarks



<b>FsRtlIncrementCcFastReadNoWait</b> increments the CcFastReadNoWait performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation, <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread~r7.md">FsRtlCopyRead</a>, was called with the <i>Wait</i> parameter set to <b>FALSE</b> indicating that the caller cannot be put into a wait state until all the data has been copied.

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlincrementccfastreadwait.md">FsRtlIncrementCcFastReadWait</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread~r7.md">FsRtlCopyRead</a>



<a href="..\ntifs\nf-ntifs-fsrtlincrementccfastreadnotpossible.md">FsRtlIncrementCcFastReadNotPossible</a>



<a href="..\ntifs\nf-ntifs-fsrtlincrementccfastreadresourcemiss.md">FsRtlIncrementCcFastReadResourceMiss</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIncrementCcFastReadNoWait routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

