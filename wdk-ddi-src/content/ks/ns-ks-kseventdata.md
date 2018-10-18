---
UID: NS:ks.KSEVENTDATA
title: KSEVENTDATA
author: windows-driver-content
description: Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method.
old-location: stream\kseventdata.htm
tech.root: stream
ms.assetid: 83503353-e4f7-47ba-9a0c-71264798e983
ms.date: 04/23/2018
ms.keywords: "*PKSEVENTDATA, KSEVENTDATA, KSEVENTDATA structure [Streaming Media Devices], PKSEVENTDATA, PKSEVENTDATA structure pointer [Streaming Media Devices], ks-struct_e9669775-4fb9-465a-bd2b-fd02f718d7a3.xml, ks/KSEVENTDATA, ks/PKSEVENTDATA, stream.kseventdata"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSEVENTDATA
product:
- Windows
targetos: Windows
req.typenames: KSEVENTDATA, *PKSEVENTDATA
---

# KSEVENTDATA structure


## -description


Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method.


## -struct-fields




### -field NotificationType

Contains flags indicating what type of notification should be performed. The following table lists all the possible values for the NotificationType member.

<table>
<tr>
<th>NotificationType Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
KSEVENTF_EVENT_HANDLE

</td>
<td>
Indicates that a Win32 synchronization or notification object handle is being passed. The KSEVENTDATA.EventHandle.Event element contains the handle.

</td>
</tr>
<tr>
<td>
KSEVENTF_SEMAPHORE_HANDLE

</td>
<td>
Indicates that a Win32 semaphore handle is being passed. The KSEVENTDATA.SemaphoreHandle.Semaphore element contains the handle.

</td>
</tr>
<tr>
<td>
KSEVENTF_EVENT_OBJECT

</td>
<td>
Indicates that a pointer to a kernel synchronization or notification object is being passed. The KSEVENTDATA.EventObject.Event element contains a pointer to this object. This is available only to kernel-mode clients.

</td>
</tr>
<tr>
<td>
KSEVENTF_SEMAPHORE_OBJECT

</td>
<td>
Indicates that a pointer to a kernel semaphore object is being passed. The KSEVENTDATA.SemaphoreObject.Semaphore element contains a pointer to this object. This is available only to kernel-mode clients.

</td>
</tr>
<tr>
<td>
KSEVENTF_DPC

</td>
<td>
Indicates that a pointer to a kernel DPC structure is being passed. The KSEVENTDATA.Dpc.Dpc element contains a pointer to the DPC. This is available only to kernel-mode clients.

</td>
</tr>
<tr>
<td>
KSEVENTF_WORKITEM

</td>
<td>
Indicates that a pointer to a kernel work item structure is being passed. The KSEVENTDATA.WorkItem.WorkQueueItem contains a pointer to the work item. This is available only to kernel-mode clients.

</td>
</tr>
<tr>
<td>
KSEVENTF_KSWORKITEM

</td>
<td>
Indicates that a pointer to a kernel streaming work item structure is being passed. The KSEVENTDATA.KsWorkItem.WorkQueueItem contains a pointer to the work item, and is queued to a previously registered kernel streaming work item. This is available only to kernel-mode clients.

</td>
</tr>
</table>
 


### -field EventHandle


### -field EventHandle.Event

Contains a handle to a synchronization event when the KSEVENT_EVENT_HANDLE flag is set.


### -field EventHandle.Reserved

Reserved and set to zero.


### -field SemaphoreHandle


### -field SemaphoreHandle.Semaphore

Contains a handle to a semaphore when the KSEVENT_SEMAPHORE_HANDLE flag is set.


### -field SemaphoreHandle.Reserved

Reserved and set to zero.


### -field SemaphoreHandle.Adjustment

Contains the adjustment to the semaphore when it is released.


### -field EventObject

 


### -field EventObject.Event

 


### -field EventObject.Increment

 


### -field EventObject.Reserved

 


### -field SemaphoreObject

 


### -field SemaphoreObject.Semaphore

 


### -field SemaphoreObject.Increment

 


### -field SemaphoreObject.Adjustment

 


### -field Dpc

 


### -field Dpc.Dpc

 


### -field Dpc.ReferenceCount

 


### -field Dpc.Reserved

 


### -field WorkItem

 


### -field WorkItem.WorkQueueItem

 


### -field WorkItem.WorkQueueType

 


### -field WorkItem.Reserved

 


### -field KsWorkItem

 


### -field KsWorkItem.WorkQueueItem

 


### -field KsWorkItem.KsWorkerObject

 


### -field KsWorkItem.Reserved

 


### -field Alignment


### -field Alignment.Unused

Not used.


### -field Alignment.Alignment

Reserved for internal use by AVStream. Minidrivers should not manipulate this member.


## -remarks



For more information, see <a href="https://msdn.microsoft.com/3eaa1d65-8417-4a07-b358-823394baec9b">KS Events</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562678">KsIncrementCountedWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566775">KsRegisterWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557304">WORK_QUEUE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566382">WORK_QUEUE_TYPE</a>
 

 

