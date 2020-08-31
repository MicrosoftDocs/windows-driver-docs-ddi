---
UID: NF:wdm.ObDereferenceObjectDeferDeleteWithTag
title: ObDereferenceObjectDeferDeleteWithTag function (wdm.h)
description: The ObDereferenceObjectDeferDeleteWithTag routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obdereferenceobjectdeferdeletewithtag.htm
tech.root: kernel
ms.assetid: 72f1622f-a364-4d93-9c49-c4c7bcda6488
ms.date: 04/30/2018
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

# ObDereferenceObjectDeferDeleteWithTag function


## -description

The <b>ObDereferenceObjectDeferDeleteWithTag</b> routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support <a href="https://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>.

## -parameters

### -param Object 

[in]
A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> routine after it opens the object.

### -param Tag 

[in]
Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -remarks

<b>ObDereferenceObjectDeferDeleteWithTag</b> is similar to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a> except that, when the reference count of the object reaches zero, <b>ObDereferenceObjectDeferDeleteWithTag</b> passes the object deletion request to a worker thread. The worker thread, which runs at IRQL = PASSIVE_LEVEL, later deletes the object.

If the immediate deletion of an object by the current thread might cause a deadlock, do not call <b>ObDereferenceObjectWithTag</b> to dereference the object. Instead, call <b>ObDereferenceObjectDeferDeleteWithTag</b> to dereference the object.

For example, such a deadlock can occur if <b>ObDereferenceObjectWithTag</b> is used to dereference a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-kernel-transaction-manager">Kernel Transaction Manager</a> (KTM) object when a higher-level driver on the driver stack is holding a lock.

For more information about object permanence and object attributes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a>. For more information about object references, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/life-cycle-of-an-object">Life Cycle of an Object</a>.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdelete">ObDereferenceObjectDeferDelete</a> routine is similar to <b>ObDereferenceObjectDeferDeleteWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObDereferenceObjectDeferDelete</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObDereferenceObjectDeferDelete</b> has the same effect as a call to <b>ObDereferenceObjectDeferDeleteWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="https://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-obtrace">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-obtrace">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="https://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-reference-tracing-with-tags">Object Reference Tracing with Tags</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdelete">ObDereferenceObjectDeferDelete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a>

