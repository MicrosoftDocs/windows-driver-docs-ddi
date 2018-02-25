---
UID: NF:ntifs.FsRtlLookupPerFileObjectContext
title: FsRtlLookupPerFileObjectContext function
author: windows-driver-content
description: For a &#0034;legacy&#0034; file system filter driver, the FsRtlLookupPerFileObjectContext function retrieves context information previously associated with a file object.
old-location: ifsk\fsrtllookupperfileobjectcontext.htm
old-project: ifsk
ms.assetid: a066d78b-f6c7-484a-9d62-3578bbd063a2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, FsRtlLookupPerFileObjectContext, FsRtlLookupPerFileObjectContext function [Installable File System Drivers], L, O, P, R, b, c, e, fsrtlref_1b9542db-9037-400a-97e2-1bcfddcd1957.xml, i, ifsk.fsrtllookupperfileobjectcontext, j, k, l, n, ntifs/FsRtlLookupPerFileObjectContext, o, p, r, s, t, u, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlLookupPerFileObjectContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlLookupPerFileObjectContext function


## -description


For a "legacy" file system filter driver, the <b>FsRtlLookupPerFileObjectContext</b> function retrieves context information previously associated with a file object.


## -syntax


````
PFSRTL_PER_FILEOBJECT_CONTEXT FsRtlLookupPerFileObjectContext(
  _In_     PFILE_OBJECT FileObject,
  _In_opt_ PVOID        OwnerId ,
  _In_opt_ PVOID        InstanceId
);
````


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

To initialize a per-file-object context structure, use the <a href="https://msdn.microsoft.com/8ed219c8-927e-47b1-8ebf-689535dea0fc">FsRtlInitPerFileObjectContext </a>macro.

To associate an initialized per-file-object context structure with a file object, use the <b>FsRtlInsertPerFileObjectContext</b> function.

To remove a per-file-object context structure that is associated with a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlremoveperfileobjectcontext.md">FsRtlRemovePerFileObjectContext</a> function.

<div class="alert"><b>Note</b>  File system minifilter drivers must not use the <b>FsRtl</b><i>Xxx</i><b>PerFileObjectContext</b> functions. Instead, minifilters can use the <b>Flt</b><i>Xxx</i><b>Context</b> functions to associate context information with a file object. For a complete list, see the <a href="..\ntifs\ns-ntifs-_fsrtl_per_fileobject_context.md">FSRTL_PER_FILEOBJECT_CONTEXT</a> topic.</div>
<div> </div>



## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlremoveperfileobjectcontext.md">FsRtlRemovePerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_fileobject_context.md">FSRTL_PER_FILEOBJECT_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperfileobjectcontext.md">FsRtlLookupPerFileObjectContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlLookupPerFileObjectContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

