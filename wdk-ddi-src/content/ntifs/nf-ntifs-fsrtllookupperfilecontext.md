---
UID: NF:ntifs.FsRtlLookupPerFileContext
title: FsRtlLookupPerFileContext function
author: windows-driver-content
description: The FsRtlLookupPerFileContext routine returns a pointer to a FSRTL_PER_FILE_CONTEXT object that is associated with a specified file.
old-location: ifsk\fsrtllookupperfilecontext.htm
old-project: ifsk
ms.assetid: b15598bd-8362-44f1-83ce-b4282d6604b0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlLookupPerFileContext, FsRtlLookupPerFileContext routine [Installable File System Drivers], fsrtlref_ab859bb7-ea43-4d55-ab37-feebddd270ff.xml, ifsk.fsrtllookupperfilecontext, ntifs/FsRtlLookupPerFileContext
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
req.irql: "<=  APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlLookupPerFileContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlLookupPerFileContext function


## -description


The <b>FsRtlLookupPerFileContext </b>routine returns a pointer to a <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> object that is associated with a specified file.


## -syntax


````
PFSRTL_PER_FILE_CONTEXT FsRtlLookupPerFileContext(
  _In_     PVOID *PerFileContextPointer,
  _In_opt_ PVOID OwnerId,
  _In_opt_ PVOID InstanceId
);
````


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer that is used by the file system runtime library (FSRTL) package to track file contexts. To retrieve this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro.


### -param OwnerId [in, optional]

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure.  The format of this variable is filter driver-specific. This parameter is optional, but must be non-<b>NULL</b> if <i>InstanceId</i> is non-<b>NULL</b>. 


### -param InstanceId [in, optional]

A pointer to a filter driver-allocated variable that can be used to distinguish among per-file context structures that are created by the same filter driver. The format of this variable is filter driver-specific. This parameter is optional.


## -returns



A pointer to the first FSRTL_PER_FILE_CONTEXT structure that matches the <i>OwnerId</i>  and <i>InstanceId</i>, if specified, or <b>NULL</b> if no match is found or the file system does not support per-file contexts.




## -remarks



By not specifying <i>OwnerID</i> and <i>InstanceId</i>, a filter driver can search for the first context that is associated with a file.  

If the file system does not support per-file context objects, <b>NULL</b> is returned. Use the <a href="..\ntifs\nf-ntifs-fsrtlsupportsperfilecontexts.md">FsRtlSupportsPerFileContexts</a> macro to determine whether a file system supports per-file context objects.




## -see-also

<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperfilecontext.md">FsRtlRemovePerFileContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md">FsRtlInsertPerFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlLookupPerFileContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

