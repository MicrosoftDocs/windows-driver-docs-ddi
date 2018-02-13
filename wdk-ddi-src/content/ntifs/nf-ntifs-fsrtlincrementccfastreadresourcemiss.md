---
UID: NF:ntifs.FsRtlIncrementCcFastReadResourceMiss
title: FsRtlIncrementCcFastReadResourceMiss function
author: windows-driver-content
description: The FsRtlIncrementCcFastReadResourceMiss routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.
old-location: ifsk\fsrtlincrementccfastreadresourcemiss.htm
old-project: ifsk
ms.assetid: 38264afe-e324-455d-b81a-7dafae8abc1c
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlIncrementCcFastReadResourceMiss routine [Installable File System Drivers], FsRtlIncrementCcFastReadResourceMiss, ifsk.fsrtlincrementccfastreadresourcemiss, ntifs/FsRtlIncrementCcFastReadResourceMiss, fsrtlref_4eb3905b-e599-451e-ba6c-29b800b277a5.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlIncrementCcFastReadResourceMiss
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIncrementCcFastReadResourceMiss function


## -description


The <b>FsRtlIncrementCcFastReadResourceMiss</b> routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters.


## -syntax


````
VOID FsRtlIncrementCcFastReadResourceMiss(
   VOID 
);
````


## -parameters








## -returns



This routine does not return a value.




## -remarks



<b>FsRtlIncrementCcFastReadResourceMiss </b>increments the CcFastReadReadResourceMiss performance counter in the per processor control block of cache manager system counters. This counter indicates that a fast I/O read operation (<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread~r7.md">FsRtlCopyRead</a>) was called, but fast I/O was not possible because the file resource could not be acquired for shared access. 

File system drivers should call this function to update the performance counter if the driver chooses to override the default fast I/O read handler.




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlincrementccfastreadwait.md">FsRtlIncrementCcFastReadWait</a>



<a href="..\ntifs\nf-ntifs-fsrtlincrementccfastreadnotpossible.md">FsRtlIncrementCcFastReadNotPossible</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread~r7.md">FsRtlCopyRead</a>



<a href="..\ntifs\nf-ntifs-fsrtlincrementccfastreadnowait.md">FsRtlIncrementCcFastReadNoWait</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIncrementCcFastReadResourceMiss routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

