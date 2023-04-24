---
UID: NF:wdm.ObDereferenceObject
title: ObDereferenceObject macro (wdm.h)
description: The ObDereferenceObject routine decrements the given object's reference count and performs retention checks.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["ObDereferenceObject macro"]
ms.keywords: ObDereferenceObject, ObDereferenceObject routine [Kernel-Mode Driver Architecture], k107_bc67abd9-66b2-4cd7-81c0-48ad0fa6c87d.xml, kernel.obdereferenceobject, wdm/ObDereferenceObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ObDereferenceObject
 - wdm/ObDereferenceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObDereferenceObject
---

## -description

The **ObDereferenceObject** routine decrements the given object's reference count and performs retention checks.

## -parameters

### -param a [in]

Pointer to the object's body.

## -remarks

**ObDereferenceObject** returns a value that is reserved for system use. Drivers must treat this value as VOID.

**ObDereferenceObject** decreases the reference count of an object by one. If the object was created as temporary (the OBJ_PERMANENT flag was not specified on creation), and the reference count reaches zero, the object can be deleted by the system.

A driver can delete a temporary object it created by decreasing its reference count to zero. A driver must never attempt to delete an object it did not create.

An object is permanent if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes).) A permanent object is created with a reference count of one, so it is not deleted when the driver dereferences it. A driver can only delete a permanent object it created by using the [ZwMakeTemporaryObject](./nf-wdm-zwmaketemporaryobject.md) routine to make it temporary. Use the following steps to delete a permanent object that you created:

1. Call **ObDereferenceObject**.

1. Call the appropriate **ZwOpen*Xxx*** or **ZwCreate*Xxx*** routine to get a handle for the object, if necessary.

1. Call [ZwMakeTemporaryObject](./nf-wdm-zwmaketemporaryobject.md) with the handle obtained in step 2.

1. Call [ZwClose](../ntifs/nf-ntifs-ntclose.md) with the handle obtained in step 2.

Use [ObDereferenceObjectDeferDelete](./nf-wdm-obdereferenceobjectdeferdelete.md) instead of **ObDereferenceObject** for any object, particularly [Kernel Transaction Manager](/windows-hardware/drivers/kernel/windows-kernel-mode-kernel-transaction-manager) (KTM) objects, when the immediate deletion by the current thread of the object (by using **ObDereferenceObject**) might result in a deadlock.

## -see-also

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[IoGetDeviceObjectPointer](./nf-wdm-iogetdeviceobjectpointer.md)

[ObDereferenceObjectDeferDelete](./nf-wdm-obdereferenceobjectdeferdelete.md)

[ZwClose](../ntifs/nf-ntifs-ntclose.md)

[ZwMakeTemporaryObject](./nf-wdm-zwmaketemporaryobject.md)