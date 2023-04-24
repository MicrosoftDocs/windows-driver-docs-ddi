---
UID: NF:wdm.ObDereferenceObjectWithTag
title: ObDereferenceObjectWithTag macro (wdm.h)
description: The ObDereferenceObjectWithTag routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
tech.root: kernel
ms.date: 03/14/2023
keywords: ["ObDereferenceObjectWithTag macro"]
ms.keywords: ObDereferenceObjectWithTag, ObDereferenceObjectWithTag routine [Kernel-Mode Driver Architecture], k107_4a4d8579-6641-4d2a-9599-9ac39c25fd91.xml, kernel.obdereferenceobjectwithtag, wdm/ObDereferenceObjectWithTag
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
 - ObDereferenceObjectWithTag
 - wdm/ObDereferenceObjectWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObDereferenceObjectWithTag
---

## -description

The **ObDereferenceObjectWithTag** routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support [object reference tracing](/windows-hardware/drivers/debugger/object-reference-tracing).

## -parameters

### -param a [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the [ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag) routine after it opens the object.

### -param t [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -remarks

**ObDereferenceObjectWithTag** returns a value that is reserved for system use. Drivers must treat this value as VOID.

A kernel-mode driver calls this routine to decrement the reference count of an object by one. If the object was created as *temporary* (that is, the OBJ_PERMANENT flag was not specified when the object was created), and the reference count reaches zero, the object manager deletes the object.

When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.

An object is *permanent* if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes).) A permanent object is created with an initial reference count of one, so the object is not deleted when the driver removes its last reference to the object.

To prepare a permanent object to be deleted, a driver can call the [ZwMakeTemporaryObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject) routine to make the object temporary. A driver should only delete a permanent object that it created. Use the following steps to delete a permanent object:

1. Call **ObDereferenceObjectWithTag**.

1. Get the handle to the object. If necessary, call the appropriate **ZwOpen*Xxx*** or **ZwCreate*Xxx*** routine to get the object handle.

1. Call **ZwMakeTemporaryObject** with the handle obtained in step 2.

1. Call [ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose) with the handle obtained in step 2.

If the immediate deletion of an object by the current thread might cause a deadlock, do not call **ObDereferenceObjectWithTag** to dereference the object. Instead, call the [ObDereferenceObjectDeferDeleteWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdeletewithtag) routine to dereference the object.

For example, such a deadlock can occur if **ObDereferenceObjectWithTag** is used to dereference a [Kernel Transaction Manager](/windows-hardware/drivers/kernel/windows-kernel-mode-kernel-transaction-manager) (KTM) object when a higher-level driver on the driver stack is holding a lock.

For more information about object references, see [Life Cycle of an Object](/windows-hardware/drivers/kernel/life-cycle-of-an-object).

The [ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject) routine is similar to **ObDereferenceObjectWithTag**, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, **ObDereferenceObject** always writes a default tag value ('tlfD') to the object. A call to **ObDereferenceObject** has the same effect as a call to **ObDereferenceObjectWithTag** that specifies *Tag* = 'tlfD'.

To view an object reference trace in the [Windows debugging tools](/windows-hardware/drivers/debugger), use the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) kernel-mode debugger extension. In Windows 7, the **!obtrace** extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the [Global Flags Editor](/windows-hardware/drivers/debugger/gflags) (Gflags) to enable object reference tracing. For more information, see [Object Reference Tracing with Tags](/windows-hardware/drivers/kernel/object-reference-tracing-with-tags).

## -see-also

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[IoGetDeviceObjectPointer](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer)

[ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject)

[ObDereferenceObjectDeferDeleteWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdeletewithtag)

[ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag)

[ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose)

[ZwMakeTemporaryObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject)
