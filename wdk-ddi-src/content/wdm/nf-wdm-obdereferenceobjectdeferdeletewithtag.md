---
UID: NF:wdm.ObDereferenceObjectDeferDeleteWithTag
title: ObDereferenceObjectDeferDeleteWithTag function (wdm.h)
description: The ObDereferenceObjectDeferDeleteWithTag routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support object reference tracing.
tech.root: kernel
ms.date: 03/14/2023
keywords: ["ObDereferenceObjectDeferDeleteWithTag function"]
ms.keywords: ObDereferenceObjectDeferDeleteWithTag, ObDereferenceObjectDeferDeleteWithTag routine [Kernel-Mode Driver Architecture], k107_c6da92e4-6a70-4f19-bd09-4308964b1e14.xml, kernel.obdereferenceobjectdeferdeletewithtag, wdm/ObDereferenceObjectDeferDeleteWithTag
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ObDereferenceObjectDeferDeleteWithTag
 - wdm/ObDereferenceObjectDeferDeleteWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObDereferenceObjectDeferDeleteWithTag
---

## -description

The **ObDereferenceObjectDeferDeleteWithTag** routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support [object reference tracing](/windows-hardware/drivers/debugger/object-reference-tracing).

## -parameters

### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the [ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag) routine after it opens the object.

### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -remarks

**ObDereferenceObjectDeferDeleteWithTag** is similar to [ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag) except that, when the reference count of the object reaches zero, **ObDereferenceObjectDeferDeleteWithTag** passes the object deletion request to a worker thread. The worker thread, which runs at IRQL = PASSIVE_LEVEL, later deletes the object.

If the immediate deletion of an object by the current thread might cause a deadlock, do not call **ObDereferenceObjectWithTag** to dereference the object. Instead, call **ObDereferenceObjectDeferDeleteWithTag** to dereference the object.

For example, such a deadlock can occur if **ObDereferenceObjectWithTag** is used to dereference a [Kernel Transaction Manager](/windows-hardware/drivers/kernel/windows-kernel-mode-kernel-transaction-manager) (KTM) object when a higher-level driver on the driver stack is holding a lock.

For more information about object permanence and object attributes, see [ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag). For more information about object references, see [Life Cycle of an Object](/windows-hardware/drivers/kernel/life-cycle-of-an-object).

The [ObDereferenceObjectDeferDelete](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdelete) routine is similar to **ObDereferenceObjectDeferDeleteWithTag**, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, **ObDereferenceObjectDeferDelete** always writes a default tag value ('tlfD') to the object. A call to **ObDereferenceObjectDeferDelete** has the same effect as a call to **ObDereferenceObjectDeferDeleteWithTag** that specifies *Tag* = 'tlfD'.

To view an object reference trace in the [Windows debugging tools](/windows-hardware/drivers/debugger), use the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) kernel-mode debugger extension. In Windows 7, the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the [Global Flags Editor](/windows-hardware/drivers/debugger/gflags) (Gflags) to enable object reference tracing. For more information, see [Object Reference Tracing with Tags](/windows-hardware/drivers/kernel/object-reference-tracing-with-tags).

## -see-also

[ObDereferenceObjectDeferDelete](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdelete)

[ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag)

[ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag)
