---
UID: NF:wdm.ObDereferenceObjectDeferDelete
title: ObDereferenceObjectDeferDelete function
author: windows-driver-content
description: The ObDereferenceObjectDeferDelete routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks.
old-location: kernel\obdereferenceobjectdeferdelete.htm
old-project: kernel
ms.assetid: 6b20db9e-807d-40f5-844f-f9726e3a854f
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ObDereferenceObjectDeferDelete, ObDereferenceObjectDeferDelete routine [Kernel-Mode Driver Architecture], k107_d20a8bd1-feff-4c48-8c6f-ccf8a119281b.xml, kernel.obdereferenceobjectdeferdelete, wdm/ObDereferenceObjectDeferDelete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows operating systems.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ObDereferenceObjectDeferDelete
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObDereferenceObjectDeferDelete function


## -description


The <b>ObDereferenceObjectDeferDelete</b> routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks.


## -syntax


````
VOID ObDereferenceObjectDeferDelete(
  _In_ PVOID Object
);
````


## -parameters




### -param Object [in]

A pointer to the body of the object.


## -returns



None




## -remarks



<b>ObDereferenceObjectDeferDelete</b> is similar to <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> except that, when the reference count of the object reaches zero, the object manager passes the object deletion request to a worker thread. Therefore, the deletion later occurs at IRQL = PASSIVE_LEVEL.

Use <b>ObDereferenceObjectDeferDelete</b> for any object when the immediate deletion by the current thread of the object (by using <b>ObDereferenceObject</b>) might result in a deadlock.

For example, such a deadlock can occur if <b>ObDereferenceObject</b> is used to dereference a <a href="https://msdn.microsoft.com/b558ace9-b416-4572-ac94-58a083c9d33b">Kernel Transaction Manager</a> (KTM) object when a higher level driver on the driver stack is holding a lock.

To avoid such deadlocks, use <b>ObDereferenceObjectDeferDelete</b> instead of <b>ObDereferenceObject</b> to dereference KTM objects.

<div class="alert"><b>Note</b>  For information about object permanence and attributes, see <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>.</div>
<div> </div>



## -see-also

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a>



 

 


