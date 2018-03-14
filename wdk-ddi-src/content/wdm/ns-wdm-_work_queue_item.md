---
UID: NS:wdm._WORK_QUEUE_ITEM
title: "_WORK_QUEUE_ITEM"
author: windows-driver-content
description: The WORK_QUEUE_ITEM structure is used to post a work items to a system work queue.
old-location: ifsk\work_queue_item.htm
old-project: ifsk
ms.assetid: 068ac200-55bb-4d7b-bc69-ad57d466a36b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWORK_QUEUE_ITEM, PWORK_QUEUE_ITEM, PWORK_QUEUE_ITEM structure pointer [Installable File System Drivers], WORK_QUEUE_ITEM, WORK_QUEUE_ITEM structure [Installable File System Drivers], _WORK_QUEUE_ITEM, ifsk.work_queue_item, othersystemstructures_52486f79-e8f4-4fb3-9b41-564bbd78f5d5.xml, wdm/PWORK_QUEUE_ITEM, wdm/WORK_QUEUE_ITEM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	WORK_QUEUE_ITEM
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_ITEM, *PWORK_QUEUE_ITEM
req.product: Windows 10 or later.
---

# _WORK_QUEUE_ITEM structure


## -description


The WORK_QUEUE_ITEM structure is used to post a work items to a system work queue. <i>Use this structure with extreme caution. (See the following </i><b>Remarks</b><i> section.)</i>


## -syntax


````
typedef struct _WORK_QUEUE_ITEM {
  LIST_ENTRY             List;
  PWORKER_THREAD_ROUTINE WorkerRoutine;
  volatile PVOID         Parameter;
} WORK_QUEUE_ITEM, *PWORK_QUEUE_ITEM;
````


## -struct-fields




### -field List

Doubly linked list structure. This structure is used to add the work item to the system work queue. 


### -field WorkerRoutine

Pointer to a callback routine that processes this work item when the work item is dequeued. This callback routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PWORKER_THREAD_ROUTINE)(
    IN PVOID Parameter
    );</pre>
</td>
</tr>
</table></span></div>




#### Parameter

Context information pointer specified in the <b>Parameter</b> member. 


### -field Parameter

Pointer to context information to be passed to the callback routine specified in the <b>WorkerRoutine</b> member. 


## -remarks



To initialize a WORK_QUEUE_ITEM structure, call <a href="..\wdm\nf-wdm-exinitializeworkitem.md">ExInitializeWorkItem</a>. 

To post the initialized work item to a system work queue, call <a href="..\wdm\nf-wdm-exqueueworkitem.md">ExQueueWorkItem</a>. 

<b>ExInitializeWorkItem</b><i> and </i><b>ExQueueWorkItem</b><i> can only be used in cases where the specified work item is not associated with any device object or device stack. In all other cases, drivers should use </i><a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a><i>, </i><a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a><i>, and </i><a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a><i>, because only these routines ensure that the device object associated with the specified work item remains available until the work item has been processed. </i>




## -see-also

<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>



<a href="..\wdm\nf-wdm-exinitializeworkitem.md">ExInitializeWorkItem</a>



<a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a>



<a href="..\wdm\nf-wdm-exqueueworkitem.md">ExQueueWorkItem</a>



<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>



 

 


