---
UID: NF:wdm.ObDereferenceObjectDeferDelete
title: ObDereferenceObjectDeferDelete function (wdm.h)
description: The ObDereferenceObjectDeferDelete routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks.
old-location: kernel\obdereferenceobjectdeferdelete.htm
tech.root: kernel
ms.assetid: 6b20db9e-807d-40f5-844f-f9726e3a854f
ms.date: 04/30/2018
keywords: ["ObDereferenceObjectDeferDelete function"]
ms.keywords: ObDereferenceObjectDeferDelete, ObDereferenceObjectDeferDelete routine [Kernel-Mode Driver Architecture], k107_d20a8bd1-feff-4c48-8c6f-ccf8a119281b.xml, kernel.obdereferenceobjectdeferdelete, wdm/ObDereferenceObjectDeferDelete
f1_keywords:
 - "wdm/ObDereferenceObjectDeferDelete"
 - "ObDereferenceObjectDeferDelete"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ObDereferenceObjectDeferDelete
targetos: Windows
req.typenames: 
---

# ObDereferenceObjectDeferDelete function


## -description


The <b>ObDereferenceObjectDeferDelete</b> routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks.


## -parameters




### -param Object [in]

A pointer to the body of the object.


## -remarks



<b>ObDereferenceObjectDeferDelete</b> is similar to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> except that, when the reference count of the object reaches zero, the object manager passes the object deletion request to a worker thread. Therefore, the deletion later occurs at IRQL = PASSIVE_LEVEL.

Use <b>ObDereferenceObjectDeferDelete</b> for any object when the immediate deletion by the current thread of the object (by using <b>ObDereferenceObject</b>) might result in a deadlock.

For example, such a deadlock can occur if <b>ObDereferenceObject</b> is used to dereference a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-kernel-transaction-manager">Kernel Transaction Manager</a> (KTM) object when a higher level driver on the driver stack is holding a lock.

To avoid such deadlocks, use <b>ObDereferenceObjectDeferDelete</b> instead of <b>ObDereferenceObject</b> to dereference KTM objects.

<div class="alert"><b>Note</b>  For information about object permanence and attributes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a>
 

 

