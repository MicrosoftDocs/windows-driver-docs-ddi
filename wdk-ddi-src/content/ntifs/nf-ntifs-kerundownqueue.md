---
UID: NF:ntifs.KeRundownQueue
title: KeRundownQueue function
author: windows-driver-content
description: The KeRundownQueue routine cleans up a queue object, flushing any queued entries.
old-location: ifsk\kerundownqueue.htm
old-project: ifsk
ms.assetid: fc496af8-0b4b-4de4-8890-f2290970ced5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: keref_d1ad3c47-a2e8-40d9-b59d-bcedd6e4314a.xml, KeRundownQueue, ifsk.kerundownqueue, ntifs/KeRundownQueue, KeRundownQueue routine [Installable File System Drivers]
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeRundownQueue
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeRundownQueue function


## -description


The <b>KeRundownQueue</b> routine cleans up a queue object, flushing any queued entries. 


## -syntax


````
PLIST_ENTRY KeRundownQueue(
  _Inout_ PRKQUEUE Queue
);
````


## -parameters




### -param Queue [in, out]

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool.


## -returns


If the queue is empty, <b>KeRundownQueue</b> returns <b>NULL</b>; otherwise, it returns the address of the first entry in the queue. 



## -remarks


File systems call <b>KeRundownQueue</b> to discard all entries from a queue before freeing or reusing the queue object.

If the queue object is to be reused, the caller must call <a href="..\ntifs\nf-ntifs-keinitializequeue.md">KeInitializeQueue</a> after calling <b>KeRundownQueue</b>, in order to reinitialize the queue object before reusing it. 

<b>KeRundownQueue</b> returns no information about how many queued entries are discarded. 

<b>KeRundownQueue</b> should never be called for a queue if any threads are waiting on the queue object.

For more information about using driver-managed internal queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544165">Driver-Managed Queues</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-keinitializequeue.md">KeInitializeQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeRundownQueue routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

