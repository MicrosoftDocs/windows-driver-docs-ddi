---
UID: NF:ntifs.FsRtlTeardownPerFileContexts
title: FsRtlTeardownPerFileContexts function
author: windows-driver-content
description: File systems call theFsRtlTeardownPerFileContexts routine to free FSRTL_PER_FILE_CONTEXT objects that are associated with a file control block (FCB) structure.
old-location: ifsk\fsrtlteardownperfilecontexts.htm
tech.root: ifsk
ms.assetid: c124c5a4-5187-4474-8896-28c729bc7d07
ms.date: 04/16/2018
ms.keywords: FsRtlTeardownPerFileContexts, FsRtlTeardownPerFileContexts routine [Installable File System Drivers], fsrtlref_3bd1af9f-ebc1-4cf8-9c7d-415f4bc64eb4.xml, ifsk.fsrtlteardownperfilecontexts, ntifs/FsRtlTeardownPerFileContexts
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting withWindows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlTeardownPerFileContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlTeardownPerFileContexts function


## -description


File systems call the<b>FsRtlTeardownPerFileContexts</b> routine to free <a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a> objects that are associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-fcb-structure">file control block (FCB)</a> structure.


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer that identifies the per file context structure. To retrieve this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro.


## -returns



None




## -remarks



This routine calls the <i>FreeCallback</i> routine specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a> object. The <i>FreeCallback</i> routine has to deallocate the <b>FSRTL_PER_FILE_CONTEXT</b> structure and the associated context.

To avoid conflicts in synchronization, the <b>FsRtlTeardownPerFileContexts</b> routine releases the lock for the per file context objects before calling <i>FreeCallback</i>. This avoids blocking access to the to the per file context objects by the filter for its own list operations, such as removal with <a href="https://msdn.microsoft.com/library/windows/hardware/ff547226">FsRtlRemovePerFileContext</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551123">PFREE_FUNCTION</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>
 

 

