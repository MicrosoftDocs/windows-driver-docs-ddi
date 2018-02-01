---
UID: NF:wdm.KeGetCurrentThread
title: KeGetCurrentThread function
author: windows-driver-content
description: The KeGetCurrentThread routine identifies the current thread.
old-location: kernel\kegetcurrentthread.htm
old-project: kernel
ms.assetid: 0fbc9f6d-698b-4fa5-86c4-3f6ef0cc50fb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_fa2d3ae9-9ac8-4c50-bf51-5d6751a2b81e.xml, KeGetCurrentThread, KeGetCurrentThread routine [Kernel-Mode Driver Architecture], kernel.kegetcurrentthread, wdm/KeGetCurrentThread
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
-	KeGetCurrentThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeGetCurrentThread function


## -description


The <b>KeGetCurrentThread</b> routine identifies the current thread. 


## -syntax


````
PKTHREAD KeGetCurrentThread(void);
````


## -parameters





## -returns


<b>KeGetCurrentThread</b> returns a pointer to an opaque thread object. 



## -remarks


This routine is identical to <a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>.

A caller of <b>KeGetCurrentThread</b> can use the returned pointer as an input parameter to <a href="..\wdm\nf-wdm-kequeryprioritythread.md">KeQueryPriorityThread</a>, <a href="..\ntddk\nf-ntddk-kesetbaseprioritythread.md">KeSetBasePriorityThread</a>, or <a href="..\wdm\nf-wdm-kesetprioritythread.md">KeSetPriorityThread</a>. However, the memory containing the thread object is opaque; that is, it is reserved for exclusive use by the operating system.



## -see-also

<a href="..\wdm\nf-wdm-kesetprioritythread.md">KeSetPriorityThread</a>

<a href="..\ntddk\nf-ntddk-kesetbaseprioritythread.md">KeSetBasePriorityThread</a>

<a href="..\wdm\nf-wdm-kequeryprioritythread.md">KeQueryPriorityThread</a>

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeGetCurrentThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

