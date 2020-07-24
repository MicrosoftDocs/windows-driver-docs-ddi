---
UID: NF:ntifs.FsRtlLookupPerFileObjectContext
title: FsRtlLookupPerFileObjectContext function (ntifs.h)
description: For a &#0034;legacy&#0034; file system filter driver, the FsRtlLookupPerFileObjectContext function retrieves context information previously associated with a file object.
old-location: ifsk\fsrtllookupperfileobjectcontext.htm
tech.root: ifsk
ms.assetid: a066d78b-f6c7-484a-9d62-3578bbd063a2
ms.date: 04/16/2018
keywords: ["FsRtlLookupPerFileObjectContext function"]
ms.keywords: FsRtlLookupPerFileObjectContext, FsRtlLookupPerFileObjectContext function [Installable File System Drivers], fsrtlref_1b9542db-9037-400a-97e2-1bcfddcd1957.xml, ifsk.fsrtllookupperfileobjectcontext, ntifs/FsRtlLookupPerFileObjectContext
f1_keywords:
 - "ntifs/FsRtlLookupPerFileObjectContext"
 - "FsRtlLookupPerFileObjectContext"
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlLookupPerFileObjectContext
targetos: Windows
req.typenames: 
---

# FsRtlLookupPerFileObjectContext function


## -description


For a "legacy" file system filter driver, the <b>FsRtlLookupPerFileObjectContext</b> function retrieves context information previously associated with a file object.


## -parameters




### -param FileObject [in]

A pointer to a file object for which to query context information.


### -param OwnerId [in, optional]

A pointer to a caller-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific.


### -param InstanceId [in, optional]

A pointer to a caller-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>FsRtlLookupPerFileObjectContext</b> returns a pointer to the first matching per-file-object context that is found. If no match is found, <b>FsRtlLookupPerFileObjectContext</b> returns <b>NULL</b>.




## -remarks



A "legacy" file system filter driver calls <b>FsRtlLookupPerFileObjectContext</b> to retrieve its per-file-object context structure for a file object. The context structure contains context information that the filter driver maintains for the file object. This context structure must have previously been associated with the file object by calling the <b>FsRtlInsertPerFileObjectContext</b> function.

If the FSRTL_PER_FILEOBJECT_CONTEXT structure is embedded in a filter defined per-file-object context structure, the <b>CONTAINING_RECORD</b> macro can be used to obtain a pointer to the head of the filter-defined structure.

To initialize a per-file-object context structure, use the <a href="https://docs.microsoft.com/previous-versions/ff546170(v=vs.85)">FsRtlInitPerFileObjectContext </a>macro.

To associate an initialized per-file-object context structure with a file object, use the <b>FsRtlInsertPerFileObjectContext</b> function.

To remove a per-file-object context structure that is associated with a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a> function.

<div class="alert"><b>Note</b>  File system minifilter drivers must not use the <b>FsRtl</b><i>Xxx</i><b>PerFileObjectContext</b> functions. Instead, minifilters can use the <b>Flt</b><i>Xxx</i><b>Context</b> functions to associate context information with a file object. For a complete list, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547346">FSRTL_PER_FILEOBJECT_CONTEXT</a> topic.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547346">FSRTL_PER_FILEOBJECT_CONTEXT</a>



<a href="https://docs.microsoft.com/previous-versions/ff546170(v=vs.85)">FsRtlInitPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a>
 

 

