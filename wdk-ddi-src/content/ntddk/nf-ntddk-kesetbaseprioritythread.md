---
UID: NF:ntddk.KeSetBasePriorityThread
title: KeSetBasePriorityThread function (ntddk.h)
description: The KeSetBasePriorityThread routine sets the run-time priority, relative to the current process, for a given thread.
old-location: kernel\kesetbaseprioritythread.htm
tech.root: kernel
ms.assetid: 7070070c-a953-4120-bddf-c1a7f080ef50
ms.date: 04/30/2018
ms.keywords: KeSetBasePriorityThread, KeSetBasePriorityThread routine [Kernel-Mode Driver Architecture], k105_6c558266-e459-447c-9586-4b327e24d7dd.xml, kernel.kesetbaseprioritythread, ntddk/KeSetBasePriorityThread
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeSetBasePriorityThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeSetBasePriorityThread function


## -description


The <b>KeSetBasePriorityThread</b> routine sets the run-time priority, relative to the current process, for a given thread.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552084">KeGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553062">KeQueryPriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553265">KeSetPriorityThread</a>
 

 

