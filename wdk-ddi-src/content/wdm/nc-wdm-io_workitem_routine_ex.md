---
UID: NC:wdm.IO_WORKITEM_ROUTINE_EX
title: IO_WORKITEM_ROUTINE_EX
author: windows-driver-content
description: A WorkItemEx routine performs the processing for a work item that was queued by the IoQueueWorkItemEx or IoTryQueueWorkItem routine.
old-location: kernel\workitemex.htm
old-project: kernel
ms.assetid: 7b40f2c8-c862-4a0b-99f6-f7d8c454b845
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: DrvrRtns_1ce116f5-d27b-4be5-800f-51ca29221223.xml, IO_WORKITEM_ROUTINE_EX, WorkItemEx, WorkItemEx routine [Kernel-Mode Driver Architecture], kernel.workitemex, wdm/WorkItemEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	WorkItemEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IO_WORKITEM_ROUTINE_EX callback function


## -description


A <i>WorkItemEx</i> routine performs the processing for a work item that was queued by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a> routine.


## -parameters




### -param IoObject [in]

Pointer to the caller's driver object or to one of the caller's device objects. This is the pointer that was passed as the <i>DeviceObject</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548276">IoAllocateWorkItem</a> when the work item was allocated, or as the <i>IoObject</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549349">IoInitializeWorkItem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a> when the work item was initialized.


### -param Context [in, optional]

Specifies driver-specific context information. This is the value that was passed as the <i>Context</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a> when the work item was queued.


### -param IoWorkItem [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure for the work item. This is the pointer that was passed as the <i>IoWorkItem</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a>.


## -returns



None




## -remarks



Drivers can implement <i>WorkItemEx</i> routines only on Windows Vista and later versions of Windows.

The driver queues a <i>WorkItemEx</i> routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a>, and a system worker thread subsequently executes the routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

A <i>WorkItemEx</i> routine must run for a limited amount of time; otherwise, the system can deadlock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

A <i>WorkItemEx</i> routine runs at IRQL = PASSIVE_LEVEL and in a system thread context. 


#### Examples

To define a <i>WorkItemEx</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>WorkItemEx</i> callback routine that is named <code>MyWorkItemEx</code>, use the IO_WORKITEM_ROUTINE_EX type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_WORKITEM_ROUTINE_EX MyWorkItemEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyWorkItemEx(
    PVOID  IoObject,
    PVOID  Context,
    PIO_WORKITEM  IoWorkItem 
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_WORKITEM_ROUTINE_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_WORKITEM_ROUTINE_EX function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549349">IoInitializeWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a>
 

 

