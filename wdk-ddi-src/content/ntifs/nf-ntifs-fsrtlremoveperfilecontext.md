---
UID: NF:ntifs.FsRtlRemovePerFileContext
title: FsRtlRemovePerFileContext function
description: The FsRtlRemovePerFileContext routine returns a pointer to a FSRTL_PER_FILE_CONTEXT object that is associated with a file.
old-location: ifsk\fsrtlremoveperfilecontext.htm
tech.root: ifsk
ms.assetid: 1a4b6759-84d9-4731-8920-ef6ea1e51102
ms.date: 04/16/2018
ms.keywords: FsRtlRemovePerFileContext, FsRtlRemovePerFileContext routine [Installable File System Drivers], fsrtlref_90f829b2-a8ed-44fd-adb3-61c57f5f9aad.xml, ifsk.fsrtlremoveperfilecontext, ntifs/FsRtlRemovePerFileContext
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
-	FsRtlRemovePerFileContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlRemovePerFileContext function


## -description


The <b>FsRtlRemovePerFileContext</b> routine returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a> object that is associated with a file. <b>FsRtlRemovePerFileContext</b> removes the <b>FSRTL_PER_FILE_CONTEXT</b> object from the list it occupies, along with the associated driver specific context information.


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer that is used by the file system runtime library (FSRTL) package to track file contexts. To obtain this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro.


### -param OwnerId [in, optional]

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure.  This parameter is optional, but must be non-<b>NULL</b> if <i>InstanceId</i> is non-<b>NULL</b>. 


### -param InstanceId [in, optional]

A pointer to a filter driver-allocated variable that can be used to distinguish among per-file context structures that are created by the same filter driver.  This parameter is optional.


## -returns



A pointer to the first <a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a> that matches the <i>OwnerId</i> and <i>InstanceId</i>, if specified. If no match is found or if the system does not support per file context information, this routine returns <b>NULL</b>.




## -remarks



<b>FsRtlRemovePerFileContext</b> removes only the first matching per-file context structure that it finds. If there are additional matching per-file contexts, the filter driver must call <b>FsRtlRemovePerFileContext</b> as many times as required to remove them all.

The file system filter driver must free the memory that is used for this context information after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a> has been removed.

Use this routine for your drivers to remove contexts only when the driver must discard per-file context information while the file is still open. Contexts are removed when a file is closed by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff547290">FsRtlTeardownPerFileContexts</a>.

<div class="alert"><b>Note</b>  <ul>
<li>
Do not use this routine inside your <i>FreeCallback</i> routine. The file system removes contexts from the list before that routine is called.

</li>
<li>
Do not use this routine inside your IRP_CLOSE handler. You will not be notified when the stream is torn down.

</li>
</ul>
</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546184">FsRtlInsertPerFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546930">FsRtlLookupPerFileContext</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>
 

 

