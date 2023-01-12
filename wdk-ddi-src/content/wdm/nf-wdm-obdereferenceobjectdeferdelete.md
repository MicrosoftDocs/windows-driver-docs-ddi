---
UID: NF:wdm.ObDereferenceObjectDeferDelete
title: ObDereferenceObjectDeferDelete function (wdm.h)
description: The ObDereferenceObjectDeferDelete routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["ObDereferenceObjectDeferDelete function"]
ms.keywords: ObDereferenceObjectDeferDelete, ObDereferenceObjectDeferDelete routine [Kernel-Mode Driver Architecture], k107_d20a8bd1-feff-4c48-8c6f-ccf8a119281b.xml, kernel.obdereferenceobjectdeferdelete, wdm/ObDereferenceObjectDeferDelete
req.header: wdm.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ObDereferenceObjectDeferDelete
 - wdm/ObDereferenceObjectDeferDelete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObDereferenceObjectDeferDelete
---

## -description

The **ObDereferenceObjectDeferDelete** routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks.

## -parameters

### -param Object [in]

A pointer to the body of the object.

## -remarks

**ObDereferenceObjectDeferDelete** is similar to [ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject) except that, when the reference count of the object reaches zero, the object manager passes the object deletion request to a worker thread. Therefore, the deletion later occurs at IRQL = PASSIVE_LEVEL.

Use **ObDereferenceObjectDeferDelete** for any object when the immediate deletion by the current thread of the object (by using **ObDereferenceObject**) might result in a deadlock.

For example, such a deadlock can occur if **ObDereferenceObject** is used to dereference a [Kernel Transaction Manager](/windows-hardware/drivers/kernel/using-kernel-transaction-manager) (KTM) object when a higher level driver on the driver stack is holding a lock.

To avoid such deadlocks, use **ObDereferenceObjectDeferDelete** instead of **ObDereferenceObject** to dereference KTM object.

For information about object permanence and attributes, see [ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject).

## -see-also

[ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject)

[ObReferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject)
