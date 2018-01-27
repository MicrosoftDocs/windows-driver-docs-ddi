---
UID: NF:wdm.KeSetPriorityThread
title: KeSetPriorityThread function
author: windows-driver-content
description: The KeSetPriorityThread routine sets the run-time priority of a driver-created thread.
old-location: kernel\kesetprioritythread.htm
old-project: kernel
ms.assetid: 400176a1-9192-424b-be37-9386cc3ffbb2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeSetPriorityThread routine [Kernel-Mode Driver Architecture], KeSetPriorityThread, kernel.kesetprioritythread, wdm/KeSetPriorityThread, k105_b767dc2c-39ec-41de-8888-177d83de67c4.xml
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	KeSetPriorityThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSetPriorityThread function


## -description


The <b>KeSetPriorityThread</b> routine sets the run-time priority of a driver-created thread.


## -syntax


````
KPRIORITY KeSetPriorityThread(
  _Inout_ PKTHREAD  Thread,
  _In_    KPRIORITY Priority
);
````


## -parameters




### -param Thread [in, out]

Pointer to the driver-created thread.


### -param Priority [in]

Specifies the priority of the driver-created thread, usually to the real-time priority value, LOW_REALTIME_PRIORITY. The value LOW_PRIORITY is reserved for system use. 


## -returns


<b>KeSetPriorityThread</b> returns the old priority of the thread.



## -remarks


If a call to <b>KeSetPriorityThread</b> resets the thread's priority to a lower value, execution of the thread can be rescheduled even if it is currently running or is about to be dispatched for execution. 



## -see-also

<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>

<a href="..\wdm\nf-wdm-kequeryprioritythread.md">KeQueryPriorityThread</a>

<a href="..\ntddk\nf-ntddk-kesetbaseprioritythread.md">KeSetBasePriorityThread</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetPriorityThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

