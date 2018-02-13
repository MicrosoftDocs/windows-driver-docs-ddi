---
UID: NF:ntddk.KeSetBasePriorityThread
title: KeSetBasePriorityThread function
author: windows-driver-content
description: The KeSetBasePriorityThread routine sets the run-time priority, relative to the current process, for a given thread.
old-location: kernel\kesetbaseprioritythread.htm
old-project: kernel
ms.assetid: 7070070c-a953-4120-bddf-c1a7f080ef50
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/KeSetBasePriorityThread, KeSetBasePriorityThread, k105_6c558266-e459-447c-9586-4b327e24d7dd.xml, KeSetBasePriorityThread routine [Kernel-Mode Driver Architecture], kernel.kesetbaseprioritythread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	KeSetBasePriorityThread
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# KeSetBasePriorityThread function


## -description


The <b>KeSetBasePriorityThread</b> routine sets the run-time priority, relative to the current process, for a given thread.


## -syntax


````
LONG KeSetBasePriorityThread(
  _Inout_ PKTHREAD Thread,
  _In_    LONG     Increment
);
````


## -parameters




### -param Thread [in, out]

Pointer to a dispatcher object of type KTHREAD. 


### -param Increment [in]

Specifies the value to be added to the base priority of the process for the <i>Thread</i>.


## -returns



<b>KeSetBasePriorityThread</b> returns the previous base priority increment of the given thread. The previous base priority increment is defined as the difference between the specified thread's old base priority and the base priority of the thread's process.




## -remarks



The new base priority is computed by adding the given <i>Increment</i>, which can be a negative value, to the base priority of the specified thread's process. The resultant value is stored as the base priority of the specified thread.

Drivers that set up device-dedicated threads with variable priority attributes can call this routine to set such a thread's priority relative to the system process in which the thread is created.

The new base priority is restricted to the priority class of the given thread's process. Therefore, the base priority is not allowed to cross over from a variable priority class to a real-time priority class or vice versa. 




## -see-also

<a href="..\wdm\nf-wdm-kequeryprioritythread.md">KeQueryPriorityThread</a>



<a href="..\wdm\nf-wdm-kesetprioritythread.md">KeSetPriorityThread</a>



<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetBasePriorityThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

