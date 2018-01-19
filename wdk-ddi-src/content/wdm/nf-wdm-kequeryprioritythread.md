---
UID: NF:wdm.KeQueryPriorityThread
title: KeQueryPriorityThread function
author: windows-driver-content
description: The KeQueryPriorityThread routine returns the current priority of a particular thread.
old-location: kernel\kequeryprioritythread.htm
old-project: kernel
ms.assetid: 69a8ad3f-641d-4aaf-9184-e56dee6ca347
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryPriorityThread
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
req.alt-api: KeQueryPriorityThread
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryPriorityThread function



## -description
The <b>KeQueryPriorityThread</b> routine returns the current priority of a particular thread. 



## -syntax

````
KPRIORITY KeQueryPriorityThread(
  _In_ PKTHREAD Thread
);
````


## -parameters

### -param Thread [in]

Pointer to a dispatcher object of type KTHREAD. 


## -returns
<b>KeQueryPriorityThread</b> returns the current priority of the specified thread. 


## -remarks
Thread priorities range from 0 to 31, where 0 is the lowest priority and 31 is the highest. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kesetbaseprioritythread.md">KeSetBasePriorityThread</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesetprioritythread.md">KeSetPriorityThread</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psgetcurrentthread.md">PsGetCurrentThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryPriorityThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

