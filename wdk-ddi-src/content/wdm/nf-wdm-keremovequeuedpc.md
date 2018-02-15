---
UID: NF:wdm.KeRemoveQueueDpc
title: KeRemoveQueueDpc function
author: windows-driver-content
description: The KeRemoveQueueDpc routine removes the specified DPC object from the system DPC queue.
old-location: kernel\keremovequeuedpc.htm
old-project: kernel
ms.assetid: 9f4b076f-006b-47cd-b970-8beed8d7e804
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_b07492b0-b6b2-4d15-b62c-437a4b33c0b6.xml, KeRemoveQueueDpc routine [Kernel-Mode Driver Architecture], KeRemoveQueueDpc, wdm/KeRemoveQueueDpc, kernel.keremovequeuedpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeRemoveQueueDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRemoveQueueDpc function


## -description


The <b>KeRemoveQueueDpc</b> routine removes the specified DPC object from the system DPC queue.


## -syntax


````
BOOLEAN KeRemoveQueueDpc(
  _Inout_ PRKDPC Dpc
);
````


## -parameters




### -param Dpc [in, out]

A pointer to an initialized DPC object that was queued by a previous call to the <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a> routine.


## -returns



<b>KeRemoveQueueDpc</b> returns <b>TRUE</b> if the DPC object is in the DPC queue. If the specified DPC object is not currently in the DPC queue, no operation is performed and <b>FALSE</b> is returned.




## -remarks



If the specified DPC object is currently queued, it is removed from the queue, canceling a call to the associated DPC routine.

Starting with Windows Vista with Service Pack 1 (SP1) and Windows Server 2008, a return value of <b>TRUE</b> always means that <b>KeRemoveQueueDpc</b> successfully removed the DPC object from the DPC queue before the DPC routine started to run. In earlier versions of Windows, the DPC routine might occasionally run even if <b>KeRemoveQueueDpc</b> returns <b>TRUE</b>. In these earlier versions of Windows, drivers that cannot tolerate ambiguity in the <b>TRUE</b> return value should treat return values of <b>TRUE</b> and <b>FALSE</b> identically.




## -see-also

<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>



<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRemoveQueueDpc routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

