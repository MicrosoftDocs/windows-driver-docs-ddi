---
UID: NF:ntifs.FsRtlRemovePerFileContext
title: FsRtlRemovePerFileContext function
author: windows-driver-content
description: The FsRtlRemovePerFileContext routine returns a pointer to a FSRTL_PER_FILE_CONTEXT object that is associated with a file.
old-location: ifsk\fsrtlremoveperfilecontext.htm
old-project: ifsk
ms.assetid: 1a4b6759-84d9-4731-8920-ef6ea1e51102
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fsrtlref_90f829b2-a8ed-44fd-adb3-61c57f5f9aad.xml, ifsk.fsrtlremoveperfilecontext, ntifs/FsRtlRemovePerFileContext, FsRtlRemovePerFileContext, FsRtlRemovePerFileContext routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlRemovePerFileContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlRemovePerFileContext function


## -description


The <b>FsRtlRemovePerFileContext</b> routine returns a pointer to a <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> object that is associated with a file. <b>FsRtlRemovePerFileContext</b> removes the <b>FSRTL_PER_FILE_CONTEXT</b> object from the list it occupies, along with the associated driver specific context information.


## -syntax


````
PFSRTL_PER_FILE_CONTEXT FsRtlRemovePerFileContext(
  _In_     PVOID *PerFileContextPointer,
  _In_opt_ PVOID OwnerId,
  _In_opt_ PVOID InstanceId
);
````


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer that is used by the file system runtime library (FSRTL) package to track file contexts. To obtain this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro.


### -param OwnerId [in, optional]

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure.  This parameter is optional, but must be non-<b>NULL</b> if <i>InstanceId</i> is non-<b>NULL</b>. 


### -param InstanceId [in, optional]

A pointer to a filter driver-allocated variable that can be used to distinguish among per-file context structures that are created by the same filter driver.  This parameter is optional.


## -returns



A pointer to the first <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> that matches the <i>OwnerId</i> and <i>InstanceId</i>, if specified. If no match is found or if the system does not support per file context information, this routine returns <b>NULL</b>.




## -remarks



<b>FsRtlRemovePerFileContext</b> removes only the first matching per-file context structure that it finds. If there are additional matching per-file contexts, the filter driver must call <b>FsRtlRemovePerFileContext</b> as many times as required to remove them all.

The file system filter driver must free the memory that is used for this context information after the <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> has been removed.

Use this routine for your drivers to remove contexts only when the driver must discard per-file context information while the file is still open. Contexts are removed when a file is closed by using <a href="..\ntifs\nf-ntifs-fsrtlteardownperfilecontexts.md">FsRtlTeardownPerFileContexts</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperfilecontext.md">FsRtlLookupPerFileContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperfilecontext.md">FsRtlLookupPerFileContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlRemovePerFileContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

