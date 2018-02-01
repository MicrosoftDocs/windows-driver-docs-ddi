---
UID: NF:wdm.ExSetResourceOwnerPointer
title: ExSetResourceOwnerPointer function
author: windows-driver-content
description: The ExSetResourceOwnerPointer routine sets the owner thread pointer for an executive resource.
old-location: kernel\exsetresourceownerpointer.htm
old-project: kernel
ms.assetid: 985f811e-cf4f-4dbe-8ede-497ba4eceffd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExSetResourceOwnerPointer routine [Kernel-Mode Driver Architecture], k102_1f5ed4f7-4252-4f50-9c40-06d6204d8b57.xml, wdm/ExSetResourceOwnerPointer, kernel.exsetresourceownerpointer, ExSetResourceOwnerPointer
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
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExSetResourceOwnerPointer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExSetResourceOwnerPointer function


## -description


The <b>ExSetResourceOwnerPointer</b> routine sets the owner thread pointer for an executive resource.


## -syntax


````
VOID ExSetResourceOwnerPointer(
  _Inout_ PERESOURCE Resource,
  _In_    PVOID      OwnerPointer
);
````


## -parameters




### -param Resource [in, out]

A pointer to an executive resource owned by the current thread.


### -param OwnerPointer [in]

A pointer to an owner thread pointer of type ERESOURCE_THREAD (for additional requirements, see the following Remarks section).


## -returns


None



## -remarks


<b>ExSetResourceOwnerPointer</b>, used in conjunction with <b>ExReleaseResourceForThreadLite</b>, provides a means for one thread (acting as an resource manager thread) to acquire and release resources for use by another thread (acting as a resource user thread).

After calling <b>ExSetResourceOwnerPointer</b> for a specific resource, the only other routine that can be called for that resource is <b>ExReleaseResourceForThreadLite</b>.

The resource manager thread acquires ownership of the resource and passes ownership to the user thread by calling <b>ExSetResourceOwnerPointer</b>. The caller must allocate the memory for the ERESOURCE_THREAD value pointed to by <i>OwnerPointer</i> in system memory, and this memory must remain allocated until <b>ExReleaseResourceForThreadLite</b> returns. The caller must also set the two low-order bits of the ERESOURCE_THREAD value pointed to by <i>OwnerPointer</i> to one — this encoding is used internally by the resource services to distinguish between owner and thread addresses.

When the user thread is done with the resource, the resource manager thread releases the user thread's ownership of the resource by calling <b>ExReleaseResourceForThreadLite</b>. The <i>ResourceThreadId</i> input parameter is set to the value of the <i>OwnerPointer</i> parameter used in the previous call to <b>ExSetResourceOwnerPointer</b> that gave the worker thread ownership of the resource.



## -see-also

<a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExSetResourceOwnerPointer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

