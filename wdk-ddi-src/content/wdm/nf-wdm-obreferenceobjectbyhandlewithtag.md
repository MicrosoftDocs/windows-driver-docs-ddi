---
UID: NF:wdm.ObReferenceObjectByHandleWithTag
title: ObReferenceObjectByHandleWithTag function (wdm.h)
description: The ObReferenceObjectByHandleWithTag routine increments the reference count of the object that is identified by the specified handle, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obreferenceobjectbyhandlewithtag.htm
tech.root: kernel
ms.assetid: f36beac8-e4fb-49ce-b49d-a1a8f32f19a5
ms.date: 04/30/2018
keywords: ["ObReferenceObjectByHandleWithTag function"]
ms.keywords: ObReferenceObjectByHandleWithTag, ObReferenceObjectByHandleWithTag routine [Kernel-Mode Driver Architecture], k107_431c6c60-e2bd-4d90-9054-b950195bbec3.xml, kernel.obreferenceobjectbyhandlewithtag, wdm/ObReferenceObjectByHandleWithTag
f1_keywords:
 - "wdm/ObReferenceObjectByHandleWithTag"
 - "ObReferenceObjectByHandleWithTag"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ObReferenceObjectByHandleWithTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# ObReferenceObjectByHandleWithTag function

## -description

The **ObReferenceObjectByHandleWithTag** routine increments the reference count of the object that is identified by the specified handle, and writes a four-byte tag value to the object to support [object reference tracing](https://docs.microsoft.com/windows-hardware/drivers/debugger/object-reference-tracing).

## -parameters

### -param Handle [in]

Specifies an open handle for an object.

### -param DesiredAccess [in]

Specifies the types of access to the object that the caller requests. This parameter is a bitmask of type [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask). The interpretation of this field depends on the object type. Do not use any generic access rights.

### -param ObjectType [in, optional]

A pointer to an opaque structure that specifies the object type. This parameter points to an [OBJECT_TYPE](https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess) structure. Set *ObjectType* to **NULL** or to one of the following pointer values, which are declared in the Wdm.h header file: \***ExEventObjectType**, \***ExSemaphoreObjectType**, \***IoFileObjectType**, \***PsProcessType**, \***PsThreadType**, \***SeTokenObjectType**, \***TmEnlistmentObjectType**, \***TmResourceManagerObjectType**, \***TmTransactionManagerObjectType**, or \***TmTransactionObjectType**. If *ObjectType* is not **NULL**, the routine verifies that the supplied object type matches the object type of the object that the *Handle* parameter specifies.

### -param AccessMode [in]

Specifies the access mode to use for the access check. It must be either **UserMode** or **KernelMode**. Drivers should always specify **UserMode** for handles they receive from user address space.

### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

### -param Object [out]

A pointer to a variable into which the routine writes a pointer to the object. The following table lists the *Object* pointer types that are designated by the possible *ObjectType* parameter values.

|*ObjectType* parameter|*Object* pointer type|
|----|----|
|\***ExEventObjectType**|PKEVENT|
|\***ExSemaphoreObjectType**|PKSEMAPHORE|
|\***IoFileObjectType**|PFILE_OBJECT|
|\***PsProcessType**|PEPROCESS or PKPROCESS|
|\***PsThreadType**|PETHREAD or PKTHREAD|
|\***SeTokenObjectType**|PACCESS_TOKEN|
|\***TmEnlistmentObjectType**|PKENLISTMENT|
|\***TmResourceManagerObjectType**|PKRESOURCEMANAGER|
|\***TmTransactionManagerObjectType**|PKTM|
|\***TmTransactionObjectType**|PKTRANSACTION|

The structures that the pointer types reference are opaque, and drivers cannot access the structure members. Because the structures are opaque, PEPROCESS is equivalent to PKPROCESS, and PETHREAD is equivalent to PKTHREAD.

### -param HandleInformation [out, optional]

Drivers set this parameter to **NULL**.

## -returns

**ObReferenceObjectByHandleWithTag** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

|Return code|Description|
|----|----|
|**STATUS_OBJECT_TYPE_MISMATCH**|The *ObjectType* parameter specifies the wrong object type for the object that is identified by the *Handle* parameter.|
|**STATUS_ACCESS_DENIED**|The caller does not have the required access rights to the object.|
|**STATUS_INVALID_HANDLE**|The specified handle is not valid.|

## -remarks

This routine does access validation of the specified object handle. If access can be granted, the routine increments the object reference count and provides an object pointer to the caller. This increment prevents the object from being deleted while the caller uses the object. When the object is no longer needed, the caller should decrement the reference count by calling the [ObDereferenceObjectWithTag](nf-wdm-obdereferenceobjectwithtag.md) or [ObDereferenceObjectDeferDeleteWithTag](nf-wdm-obdereferenceobjectdeferdeletewithtag.md) routine.

For more information about object references, see [Life Cycle of an Object](https://docs.microsoft.com/windows-hardware/drivers/kernel/life-cycle-of-an-object).

**ObReferenceObjectByHandleWithTag** does not close or invalidate the object handle that is specified by the *Handle* parameter. When the handle is no longer needed, the caller can close the handle by calling the [ZwClose](nf-wdm-zwclose.md) routine.

If the *AccessMode* parameter value is **KernelMode**, the requested access is always allowed. If *AccessMode* is **UserMode**, the requested access is compared to the access rights that the caller has to the object. Only highest-level drivers can safely specify the **UserMode** value for the *AccessMode* parameter.

Starting with Windows 7, if *AccessMode* is **KernelMode** and handle is received from user address space, [Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier) issues bugcheck C4, subcode F6.

The [ObReferenceObjectByHandle](nf-wdm-obreferenceobjectbyhandle.md) routine is similar to **ObReferenceObjectByHandleWithTag**, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, **ObReferenceObjectByHandle** always writes a default tag value ('tlfD') to the object. A call to **ObReferenceObjectByHandle** has the same effect as a call to **ObReferenceObjectByHandleWithTag** that specifies *Tag* = 'tlfD'.

To view an object reference trace in the [Windows debugging tools](https://docs.microsoft.com/windows-hardware/drivers/debugger/), use the [!obtrace](https://docs.microsoft.com/windows-hardware/drivers/debugger/-obtrace) kernel-mode debugger extension. The **!obtrace** extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the [Global Flags Editor](https://docs.microsoft.com/windows-hardware/drivers/debugger/gflags) (Gflags) to enable object reference tracing. For more information, see [Object Reference Tracing with Tags](https://docs.microsoft.com/windows-hardware/drivers/kernel/object-reference-tracing-with-tags).

## -see-also

[ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[OBJECT_TYPE](https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess)

[ObDereferenceObjectDeferDeleteWithTag](nf-wdm-obdereferenceobjectdeferdeletewithtag.md)

[ObDereferenceObjectWithTag](nf-wdm-obdereferenceobjectwithtag.md)

[ObReferenceObjectByHandle](nf-wdm-obreferenceobjectbyhandle.md)

[ZwClose](nf-wdm-zwclose.md)
