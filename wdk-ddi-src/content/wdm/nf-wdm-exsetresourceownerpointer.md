---
UID: NF:wdm.ExSetResourceOwnerPointer
title: ExSetResourceOwnerPointer function (wdm.h)
description: The ExSetResourceOwnerPointer routine sets the owner thread pointer for an executive resource.
old-location: kernel\exsetresourceownerpointer.htm
tech.root: kernel
ms.assetid: 985f811e-cf4f-4dbe-8ede-497ba4eceffd
ms.date: 04/30/2018
ms.keywords: ExSetResourceOwnerPointer, ExSetResourceOwnerPointer routine [Kernel-Mode Driver Architecture], k102_1f5ed4f7-4252-4f50-9c40-06d6204d8b57.xml, kernel.exsetresourceownerpointer, wdm/ExSetResourceOwnerPointer
f1_keywords:
 - "wdm/ExSetResourceOwnerPointer"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExSetResourceOwnerPointer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExSetResourceOwnerPointer function


## -description


The <b>ExSetResourceOwnerPointer</b> routine sets the owner thread pointer for an executive resource.


## -parameters




### -param Resource [in, out]

A pointer to an executive resource owned by the current thread.


### -param OwnerPointer [in]

A pointer to an owner thread pointer of type ERESOURCE_THREAD (for additional requirements, see the following Remarks section).


## -remarks



<b>ExSetResourceOwnerPointer</b>, used in conjunction with <b>ExReleaseResourceForThreadLite</b>, provides a means for one thread (acting as an resource manager thread) to acquire and release resources for use by another thread (acting as a resource user thread).

After calling <b>ExSetResourceOwnerPointer</b> for a specific resource, the only other routine that can be called for that resource is <b>ExReleaseResourceForThreadLite</b>.

The resource manager thread acquires ownership of the resource and passes ownership to the user thread by calling <b>ExSetResourceOwnerPointer</b>. The caller must allocate the memory for the ERESOURCE_THREAD value pointed to by <i>OwnerPointer</i> in system memory, and this memory must remain allocated until <b>ExReleaseResourceForThreadLite</b> returns. The caller must also set the two low-order bits of the ERESOURCE_THREAD value pointed to by <i>OwnerPointer</i> to one — this encoding is used internally by the resource services to distinguish between owner and thread addresses.

When the user thread is done with the resource, the resource manager thread releases the user thread's ownership of the resource by calling <b>ExReleaseResourceForThreadLite</b>. The <i>ResourceThreadId</i> input parameter is set to the value of the <i>OwnerPointer</i> parameter used in the previous call to <b>ExSetResourceOwnerPointer</b> that gave the worker thread ownership of the resource.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>
 

 

