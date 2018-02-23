---
UID: NF:wdm.KeFlushQueuedDpcs
title: KeFlushQueuedDpcs function
author: windows-driver-content
description: The KeFlushQueuedDpcs routine returns after all queued DPCs on all processors have executed.
old-location: kernel\keflushqueueddpcs.htm
old-project: kernel
ms.assetid: e5237e44-fff1-4928-9029-f1d1691ef2e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.keflushqueueddpcs, KeFlushQueuedDpcs, k105_6aaf8f1a-0fa7-422a-b390-ba0f92558a65.xml, KeFlushQueuedDpcs routine [Kernel-Mode Driver Architecture], wdm/KeFlushQueuedDpcs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP with SP2 and Windows Server 2003.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeFlushQueuedDpcs
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeFlushQueuedDpcs function


## -description


The <b>KeFlushQueuedDpcs</b> routine returns after all queued DPCs on all processors have executed.


## -syntax


````
VOID KeFlushQueuedDpcs(void);
````


## -parameters






## -returns



None




## -remarks



Drivers can use this routine to wait until all currently-queued DPCs are run. Note that <b>KeFlushQueuedDpcs</b> can take a long time to return, so drivers should not use it along any critical code paths.




## -see-also

<a href="..\wdm\nf-wdm-ioinitializedpcrequest.md">IoInitializeDpcRequest</a>



<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



<a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a>



<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeFlushQueuedDpcs routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

