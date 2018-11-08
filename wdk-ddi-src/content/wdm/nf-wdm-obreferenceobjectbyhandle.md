---
UID: NF:wdm.ObReferenceObjectByHandle
title: ObReferenceObjectByHandle function
author: windows-driver-content
description: The ObReferenceObjectByHandle routine provides access validation on the object handle, and, if access can be granted, returns the corresponding pointer to the object's body.
old-location: kernel\obreferenceobjectbyhandle.htm
tech.root: kernel
ms.assetid: 6397d96e-f3b1-4e2f-91ce-b123c9e8de81
ms.date: 04/30/2018
ms.keywords: ObReferenceObjectByHandle, ObReferenceObjectByHandle routine [Kernel-Mode Driver Architecture], k107_97ce2cea-8f20-4b30-996c-9ea268951aef.xml, kernel.obreferenceobjectbyhandle, wdm/ObReferenceObjectByHandle
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlObPassive, TargetRelationNeedsRef, HwStorPortProhibitedDDIs
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ObReferenceObjectByHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# ObReferenceObjectByHandle function

## -description

The **ObReferenceObjectByHandle** routine provides access validation on the object handle, and, if access can be granted, returns the corresponding pointer to the object's body.

## -parameters

### -param Handle [in]

Specifies an open handle for an object.

### -param DesiredAccess [in]

Specifies the requested types of access to the object. The interpretation of this field is dependent on the object type. Do not use any generic access rights. For more information, see [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask).

### -param ObjectType [in, optional]

Pointer to the object type. *ObjectType* can be **\*ExEventObjectType**, **\*ExSemaphoreObjectType**, **\*IoFileObjectType**, **\*PsProcessType**, **\*PsThreadType**, **\*SeTokenObjectType**, **\*TmEnlistmentObjectType**, **\*TmResourceManagerObjectType**, **\*TmTransactionManagerObjectType**, or **\*TmTransactionObjectType**.

If *ObjectType* is not **NULL**, the operating system verifies that the supplied object type matches the object type of the object that *Handle* specifies.

### -param AccessMode [in]

Specifies the access mode to use for the access check. It must be either **UserMode** or **KernelMode**. Drivers should always specify **UserMode** for handles they receive from user address space.

### -param Object [out]

Pointer to a variable that receives a pointer to the object's body. The following table contains the pointer types.

|ObjectType parameter|Object pointer type|
|----|----|
|**\*ExEventObjectType**|PKEVENT|
|**\*ExSemaphoreObjectType**|PKSEMAPHORE|
|**\*IoFileObjectType**|PFILE_OBJECT|
|**\*PsProcessType**|PEPROCESS or PKPROCESS|
|**\*PsThreadType**|PETHREAD or PKTHREAD|
|**\*SeTokenObjectType**|PACCESS_TOKEN|
|**\*TmEnlistmentObjectType**|PKENLISTMENT|
|**\*TmResourceManagerObjectType**|PKRESOURCEMANAGER|
|**\*TmTransactionManagerObjectType**|PKTM|
|**\*TmTransactionObjectType**|PKTRANSACTION|

The structures that the pointer types reference are opaque, and drivers cannot access the structure members. Because the structures are opaque, PEPROCESS is equivalent to PKPROCESS, and PETHREAD is equivalent to PKTHREAD.

### -param HandleInformation [out, optional]

Drivers set this to **NULL**.

## -returns

**ObReferenceObjectByHandle** returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes:

|Return code|Description|
|----|----|
|**STATUS_OBJECT_TYPE_MISMATCH**|The *ObjectType* parameter specifies the wrong object type for the object that is identified by the *Handle* parameter.|
|**STATUS_ACCESS_DENIED**|The caller cannot be granted the requested access rights to the object.|
|**STATUS_INVALID_HANDLE**|The *Handle* parameter is not a valid object handle.|

## -remarks

A pointer to the object body is retrieved from the object table entry and returned to the caller by means of the *Object* parameter.

If *AccessMode* is **UserMode**, the requested access is compared to the granted access for the object. If *AccessMode* is **KernelMode**, the handle should originate in the kernel address space.

Starting with Windows 7, if *AccessMode* is **KernelMode** and handle is received from user address space, [Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier) issues bugcheck C4, subcode F6.

If the call succeeds, a pointer to the object body is returned to the caller and the pointer reference count is incremented. Incrementing this count prevents the object from being deleted while the pointer is being referenced. The caller must decrement the reference count with [ObDereferenceObject](nf-wdm-obdereferenceobject.md) as soon as it is done with the object.

## -see-also

[ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[ObDereferenceObject](nf-wdm-obdereferenceobject.md)

[ObReferenceObject](nf-wdm-obfreferenceobject.md)

[ObReferenceObjectByPointer](nf-wdm-obreferenceobjectbypointer.md)
