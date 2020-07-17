---
UID: NF:ntifs.FsRtlLookupPerFileContext
title: FsRtlLookupPerFileContext function (ntifs.h)
description: The FsRtlLookupPerFileContext routine returns a pointer to a FSRTL_PER_FILE_CONTEXT object that is associated with a specified file.
old-location: ifsk\fsrtllookupperfilecontext.htm
tech.root: ifsk
ms.assetid: b15598bd-8362-44f1-83ce-b4282d6604b0
ms.date: 04/16/2018
keywords: ["FsRtlLookupPerFileContext function"]
ms.keywords: FsRtlLookupPerFileContext, FsRtlLookupPerFileContext routine [Installable File System Drivers], fsrtlref_ab859bb7-ea43-4d55-ab37-feebddd270ff.xml, ifsk.fsrtllookupperfilecontext, ntifs/FsRtlLookupPerFileContext
f1_keywords:
 - "ntifs/FsRtlLookupPerFileContext"
 - "FsRtlLookupPerFileContext"
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
req.irql: <=  APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlLookupPerFileContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlLookupPerFileContext function


## -description


The <b>FsRtlLookupPerFileContext </b>routine returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a> object that is associated with a specified file.


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer that is used by the file system runtime library (FSRTL) package to track file contexts. To retrieve this pointer from a file object, use the <a href="https://docs.microsoft.com/previous-versions/ff546051(v=vs.85)">FsRtlGetPerFileContextPointer</a> macro.


### -param OwnerId [in, optional]

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure.  The format of this variable is filter driver-specific. This parameter is optional, but must be non-<b>NULL</b> if <i>InstanceId</i> is non-<b>NULL</b>. 


### -param InstanceId [in, optional]

A pointer to a filter driver-allocated variable that can be used to distinguish among per-file context structures that are created by the same filter driver. The format of this variable is filter driver-specific. This parameter is optional.


## -returns



A pointer to the first FSRTL_PER_FILE_CONTEXT structure that matches the <i>OwnerId</i>  and <i>InstanceId</i>, if specified, or <b>NULL</b> if no match is found or the file system does not support per-file contexts.




## -remarks



By not specifying <i>OwnerID</i> and <i>InstanceId</i>, a filter driver can search for the first context that is associated with a file.  

If the file system does not support per-file context objects, <b>NULL</b> is returned. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlsupportsperfilecontexts">FsRtlSupportsPerFileContexts</a> macro to determine whether a file system supports per-file context objects.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547352">FSRTL_PER_FILE_CONTEXT</a>



<a href="https://docs.microsoft.com/previous-versions/ff546051(v=vs.85)">FsRtlGetPerFileContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546184">FsRtlInsertPerFileContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547226">FsRtlRemovePerFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver">Tracking Per-File Context in a Legacy File System Filter Driver</a>
 

 

