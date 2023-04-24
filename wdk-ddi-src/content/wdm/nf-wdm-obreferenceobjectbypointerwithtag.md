---
UID: NF:wdm.ObReferenceObjectByPointerWithTag
title: ObReferenceObjectByPointerWithTag function (wdm.h)
description: The ObReferenceObjectByPointerWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
tech.root: kernel
ms.date: 03/14/2023
keywords: ["ObReferenceObjectByPointerWithTag function"]
ms.keywords: ObReferenceObjectByPointerWithTag, ObReferenceObjectByPointerWithTag routine [Kernel-Mode Driver Architecture], k107_5e5e16de-36ff-4a81-9fe6-9602053ccc6b.xml, kernel.obreferenceobjectbypointerwithtag, wdm/ObReferenceObjectByPointerWithTag
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
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
 - ObReferenceObjectByPointerWithTag
 - wdm/ObReferenceObjectByPointerWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObReferenceObjectByPointerWithTag
---

## -description

The **ObReferenceObjectByPointerWithTag** routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support [object reference tracing](/windows-hardware/drivers/debugger/object-reference-tracing).

## -parameters

### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the [ObReferenceObjectByHandleWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag) routine after it opens the object.

### -param DesiredAccess [in]

Specifies the types of access to the object that the caller requests. This parameter is a bitmask of type [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask). The interpretation of this field depends on the object type. Do not use any generic access rights.

### -param ObjectType [in, optional]

A pointer to an opaque structure that specifies the object type. This parameter points to an [OBJECT_TYPE](/windows-hardware/drivers/kernel/eprocess) structure. Set *ObjectType* to **NULL** or to one of the following pointer values, which are declared in the Wdm.h header file: ***ExEventObjectType**, ***ExSemaphoreObjectType**, ***IoFileObjectType**, ***PsProcessType**, ***PsThreadType**, ***SeTokenObjectType**, ***TmEnlistmentObjectType**, ***TmResourceManagerObjectType**, ***TmTransactionManagerObjectType**, or ***TmTransactionObjectType**. This parameter can be **NULL** if *AccessMode* is **KernelMode**. If *ObjectType* is not **NULL**, the routine verifies that the supplied object type matches the object type of the object that the *Handle* parameter specifies.

### -param AccessMode [in]

Indicates the access mode to use for the access check. Set this parameter to one of the following **MODE** enumeration values:

- **UserMode**

- **KernelMode**

Lower-level drivers should specify **KernelMode**.

### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -returns

**ObReferenceObjectByPointerWithTag** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

| Return code | Description |
|---|---|
| **STATUS_OBJECT_TYPE_MISMATCH** | The *ObjectType* parameter specifies the wrong object type for the object that the *Object* parameter points to, or *ObjectType* is **NULL** but *AccessMode* is **UserMode**. |

## -remarks

This routine does access validation of the specified object. If access can be granted, the routine increments the object reference count. This increment prevents the object from being deleted while the caller uses the object. When the object is no longer needed, the caller should decrement the reference count by calling the [ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag) or [ObDereferenceObjectDeferDeleteWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdeletewithtag) routine.

For more information about object references, see [Life Cycle of an Object](/windows-hardware/drivers/kernel/life-cycle-of-an-object).

The [ObReferenceObjectByPointer](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbypointer) routine is similar to **ObReferenceObjectByPointerWithTag**, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, **ObReferenceObjectByPointer** always writes a default tag value ('tlfD') to the object. A call to **ObReferenceObjectByPointer** has the same effect as a call to **ObReferenceObjectByPointerWithTag** that specifies *Tag* = 'tlfD'.

To view an object reference trace in the [Windows debugging tools](/windows-hardware/drivers/debugger), use the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) kernel-mode debugger extension. In Windows 7, the [!obtrace](/windows-hardware/drivers/debugger/-obtrace) extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the [Global Flags Editor](/windows-hardware/drivers/debugger/gflags) (Gflags) to enable object reference tracing. For more information, see [Object Reference Tracing with Tags](/windows-hardware/drivers/kernel/object-reference-tracing-with-tags).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[OBJECT_TYPE](/windows-hardware/drivers/kernel/eprocess)

[ObDereferenceObjectDeferDeleteWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdeletewithtag)

[ObDereferenceObjectWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectwithtag)

[ObReferenceObjectByPointer](/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbypointer)

[ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose)
