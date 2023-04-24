---
UID: NF:wdm.ObReferenceObjectWithTag
title: ObReferenceObjectWithTag macro (wdm.h)
description: The ObReferenceObjectWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
tech.root: kernel
ms.date: 03/14/2023
keywords: ["ObReferenceObjectWithTag macro"]
ms.keywords: ObReferenceObjectWithTag, ObReferenceObjectWithTag routine [Kernel-Mode Driver Architecture], k107_a35c78fa-edf5-4a93-908b-baf16718b095.xml, kernel.obreferenceobjectwithtag, wdm/ObReferenceObjectWithTag
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
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
 - ObReferenceObjectWithTag
 - wdm/ObReferenceObjectWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObReferenceObjectWithTag
---

## -description

The **ObReferenceObjectWithTag** routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support [object reference tracing](/windows-hardware/drivers/debugger/object-reference-tracing).

## -parameters

### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the [ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag) routine after it opens the object.

### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -remarks

**ObReferenceObjectWithTag** returns a value that is reserved for system use. Drivers must treat this value as VOID.

**ObReferenceObjectWithTag** simply increments the pointer reference count for an object, without making any access checks on the specified object. In contrast, the [ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag) and [ObReferenceObjectByPointerWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbypointerwithtag) routines verify that the caller has the required access rights to the object and fail if the caller does not have these rights.

A **ObReferenceObjectWithTag** call prevents deletion of the specified object at least until the driver either calls the [ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag) routine, or closes the object. After the object is no longer needed, the driver must call **ObDereferenceObjectWithTag** to remove its reference to the object.

When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.

For more information about object references, see [Life Cycle of an Object](/windows-hardware/drivers/kernel/life-cycle-of-an-object).

The [ObReferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject) routine is similar to **ObReferenceObjectWithTag**, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, **ObReferenceObject** always writes a default tag value ('tlfD') to the object. A call to **ObReferenceObject** has the same effect as a call to **ObReferenceObjectWithTag** that specifies *Tag* = 'tlfD'.

To view an object reference trace in the [Windows debugging tools](/windows-hardware/drivers/debugger), use the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) kernel-mode debugger extension. In Windows 7, the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the [Global Flags Editor](/windows-hardware/drivers/debugger/gflags) (Gflags) to enable object reference tracing. For more information, see [Object Reference Tracing with Tags](/windows-hardware/drivers/kernel/object-reference-tracing-with-tags).

## -see-also

[ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag)

[ObReferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject)

[ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag)

[ObReferenceObjectByPointerWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbypointerwithtag)
