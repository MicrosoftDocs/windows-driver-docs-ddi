---
UID: NF:wdm.ObGetObjectSecurity
title: ObGetObjectSecurity function (wdm.h)
description: The ObGetObjectSecurity routine gets the security descriptor for a given object.
old-location: kernel\obgetobjectsecurity.htm
tech.root: kernel
ms.assetid: 8ac8d3ff-68ec-4e23-bbf9-0a9b7fa13ce3
ms.date: 04/30/2018
ms.keywords: ObGetObjectSecurity, ObGetObjectSecurity routine [Kernel-Mode Driver Architecture], k107_a0c800de-984a-427f-b308-415f831e5d34.xml, kernel.obgetobjectsecurity, wdm/ObGetObjectSecurity
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlApcLte, HwStorPortProhibitedDDIs
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
-	ObGetObjectSecurity
product:
- Windows
targetos: Windows
req.typenames: 
---

# ObGetObjectSecurity function

## -description

The **ObGetObjectSecurity** routine gets the security descriptor for a given object.

## -parameters

### -param Object [in]

Pointer to the object.

### -param SecurityDescriptor [out]

Pointer to a caller-supplied variable that this routine sets to the address of a buffer containing the [SECURITY_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor) for the given object. If the given object has no security descriptor, this variable is set to **NULL** on return from **ObGetObjectSecurity**.

### -param MemoryAllocated [out]

Pointer to a caller-supplied variable that this routine sets to **TRUE** if it allocated a buffer to contain the security descriptor.

## -returns

**ObGetObjectSecurity** either returns STATUS_SUCCESS or an error status, such as STATUS_INSUFFICIENT_RESOURCES if it could not allocate enough memory to return the requested information. 

## -remarks

A successful call to **ObGetObjectSecurity** either returns a self-relative security descriptor in the buffer at *\*SecurityDescriptor* or it returns **NULL** at *\*SecurityDescriptor* if the given object has no security descriptor. For example, any unnamed object, such as an event object, has no security descriptor.

If **ObGetObjectSecurity** returns STATUS_SUCCESS, the caller must save the value returned at *MemoryAllocated*. Such a caller must pass *MemoryAllocated* in a reciprocal call to [ObReleaseObjectSecurity](nf-wdm-obreleaseobjectsecurity.md) eventually, thereby restoring the reference count on the security descriptor to its original value and releasing the buffer, if any, that was allocated by **ObGetObjectSecurity**. 

**ObGetObjectSecurity** should only be called at IRQL Level = PASSIVE_LEVEL with APCs enabled, otherwise deadlocks or crashes may occur.

## -see-also

[ObReferenceObjectByHandle](nf-wdm-obreferenceobjectbyhandle.md)

[ObReleaseObjectSecurity](nf-wdm-obreleaseobjectsecurity.md)

[SECURITY_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor)
