---
UID: NF:ntifs.FsRtlTeardownPerFileContexts
title: FsRtlTeardownPerFileContexts function
author: windows-driver-content
description: File systems call theFsRtlTeardownPerFileContexts routine to free FSRTL_PER_FILE_CONTEXT objects that are associated with a file control block (FCB) structure.
old-location: ifsk\fsrtlteardownperfilecontexts.htm
old-project: ifsk
ms.assetid: c124c5a4-5187-4474-8896-28c729bc7d07
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlTeardownPerFileContexts routine [Installable File System Drivers], ifsk.fsrtlteardownperfilecontexts, FsRtlTeardownPerFileContexts, fsrtlref_3bd1af9f-ebc1-4cf8-9c7d-415f4bc64eb4.xml, ntifs/FsRtlTeardownPerFileContexts
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlTeardownPerFileContexts
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlTeardownPerFileContexts function


## -description


File systems call the<b>FsRtlTeardownPerFileContexts</b> routine to free <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> objects that are associated with a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">file control block (FCB)</a> structure.


## -syntax


````
VOID FsRtlTeardownPerFileContexts(
  _In_ PVOID *PerFileContextPointer
);
````


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer that identifies the per file context structure. To retrieve this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro.


## -returns



None




## -remarks



This routine calls the <i>FreeCallback</i> routine specified in the <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> object. The <i>FreeCallback</i> routine has to deallocate the <b>FSRTL_PER_FILE_CONTEXT</b> structure and the associated context.

To avoid conflicts in synchronization, the <b>FsRtlTeardownPerFileContexts</b> routine releases the lock for the per file context objects before calling <i>FreeCallback</i>. This avoids blocking access to the to the per file context objects by the filter for its own list operations, such as removal with <a href="..\ntifs\nf-ntifs-fsrtlremoveperfilecontext.md">FsRtlRemovePerFileContext</a>.




## -see-also

<a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551123">PFREE_FUNCTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlTeardownPerFileContexts routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

