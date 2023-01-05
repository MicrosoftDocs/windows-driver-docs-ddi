---
UID: NF:wdm.ObReferenceObjectByPointer
title: ObReferenceObjectByPointer function (wdm.h)
description: The ObReferenceObjectByPointer routine increments the pointer reference count for a given object.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["ObReferenceObjectByPointer function"]
ms.keywords: ObReferenceObjectByPointer, ObReferenceObjectByPointer routine [Kernel-Mode Driver Architecture], k107_2846f148-4ad5-472a-aa74-4f03c5251aee.xml, kernel.obreferenceobjectbypointer, wdm/ObReferenceObjectByPointer
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: TargetRelationNeedsRef, HwStorPortProhibitedDDIs
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
 - ObReferenceObjectByPointer
 - wdm/ObReferenceObjectByPointer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObReferenceObjectByPointer
---

## -description

The **ObReferenceObjectByPointer** routine increments the pointer reference count for a given object.

## -parameters

### -param Object [in]

Pointer to the object's body.

### -param DesiredAccess [in]

Specifies a mask representing the requested access to the object.

### -param ObjectType [in, optional]

Pointer to the object type. *ObjectType* can be ***ExEventObjectType**, ***ExSemaphoreObjectType**, ***IoFileObjectType**, ***PsProcessType**, ***PsThreadType**, ***SeTokenObjectType**, ***TmEnlistmentObjectType**, ***TmResourceManagerObjectType**, ***TmTransactionManagerObjectType**, or ***TmTransactionObjectType**.

This parameter can also be **NULL** if *AccessMode* is **KernelMode**.

### -param AccessMode [in]

Indicates the access mode to use for the access check. It must be either **UserMode** or **KernelMode**. Lower-level drivers should specify **KernelMode**.

## -returns

**ObReferenceObjectByPointer** returns STATUS_SUCCESS when the routine has successfully incremented the reference count of the target object's body. The routine performs object type validation if the call is being performed in user mode and if the type requested by the caller doesn't match with the one from the object's body, STATUS_OBJECT_TYPE_MISMATCH is returned.
The same NTSTATUS code is returned if the requested type is a symbolic link type (**ObpSymbolicLinkObjectType**) which is not allowed by the routine, regardless of what kind of access mode is.

## -remarks

Calling this routine prevents the object from being deleted, possibly by another component's call to [ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject) or [ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose). The caller must decrement the reference count with **ObDereferenceObject** as soon as it is done with the object.

## -see-also

[ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject)

[ObReferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obfreferenceobject)

[ObReferenceObjectByHandle](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle)

[ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose)
