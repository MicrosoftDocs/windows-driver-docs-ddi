---
UID: NF:wdm.ObGetObjectSecurity
title: ObGetObjectSecurity function
author: windows-driver-content
description: The ObGetObjectSecurity routine gets the security descriptor for a given object.
old-location: kernel\obgetobjectsecurity.htm
old-project: kernel
ms.assetid: 8ac8d3ff-68ec-4e23-bbf9-0a9b7fa13ce3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ObGetObjectSecurity, ObGetObjectSecurity routine [Kernel-Mode Driver Architecture], k107_a0c800de-984a-427f-b308-415f831e5d34.xml, kernel.obgetobjectsecurity, wdm/ObGetObjectSecurity
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObGetObjectSecurity function


## -description


The <b>ObGetObjectSecurity</b> routine gets the security descriptor for a given object. 


## -parameters




### -param Object [in]

Pointer to the object.


### -param SecurityDescriptor [out]

Pointer to a caller-supplied variable that this routine sets to the address of a buffer containing the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> for the given object. If the given object has no security descriptor, this variable is set to <b>NULL</b> on return from <b>ObGetObjectSecurity</b>.


### -param MemoryAllocated [out]

Pointer to a caller-supplied variable that this routine sets to <b>TRUE</b> if it allocated a buffer to contain the security descriptor. 


## -returns



<b>ObGetObjectSecurity</b> either returns STATUS_SUCCESS or an error status, such as STATUS_INSUFFICIENT_RESOURCES if it could not allocate enough memory to return the requested information. 




## -remarks



A successful call to <b>ObGetObjectSecurity</b> either returns a self-relative security descriptor in the buffer at *<i>SecurityDescriptor</i> or it returns <b>NULL</b> at <b>*</b><i>SecurityDescriptor</i> if the given object has no security descriptor. For example, any unnamed object, such as an event object, has no security descriptor.

If <b>ObGetObjectSecurity</b> returns STATUS_SUCCESS, the caller must save the value returned at <i>MemoryAllocated</i>. Such a caller must pass <i>MemoryAllocated</i> in a reciprocal call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff558695">ObReleaseObjectSecurity</a> eventually, thereby restoring the reference count on the security descriptor to its original value and releasing the buffer, if any, that was allocated by <b>ObGetObjectSecurity</b>. 

<b>ObGetObjectSecurity</b> should only be called at IRQL Level = PASSIVE_LEVEL with APCs enabled, otherwise deadlocks or crashes may occur.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558695">ObReleaseObjectSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>
 

 

