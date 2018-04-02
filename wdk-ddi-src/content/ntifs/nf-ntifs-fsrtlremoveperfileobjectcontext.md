---
UID: NF:ntifs.FsRtlRemovePerFileObjectContext
title: FsRtlRemovePerFileObjectContext function
author: windows-driver-content
description: For a &#0034;legacy&#0034; file system filter driver, the FsRtlRemovePerFileObjectContext function unlinks a per-file-object context information structure from the list of per-file-object contexts previously associated with a file object.
old-location: ifsk\fsrtlremoveperfileobjectcontext.htm
old-project: ifsk
ms.assetid: 84d359db-08d7-4f42-b912-02f3d483aa05
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlRemovePerFileObjectContext, FsRtlRemovePerFileObjectContext function [Installable File System Drivers], fsrtlref_2ff0b1e9-cbe5-46be-b571-3a328284b14d.xml, ifsk.fsrtlremoveperfileobjectcontext, ntifs/FsRtlRemovePerFileObjectContext
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlRemovePerFileObjectContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlRemovePerFileObjectContext function


## -description


For a "legacy" file system filter driver, the <b>FsRtlRemovePerFileObjectContext</b> function unlinks a per-file-object context information structure from the list of per-file-object contexts previously associated with a file object.


## -parameters




### -param FileObject [in]

A pointer to a file object for which to remove context information.


### -param OwnerId [in, optional]

A pointer to a caller-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific.


### -param InstanceId [in, optional]

A pointer to a caller-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>FsRtlRemovePerFileObjectContext</b> unlinks and returns a pointer to the first matching per-file-object context that is found. If no match is found, <b>FsRtlRemovePerFileObjectContext</b> returns <b>NULL</b>.




## -remarks



A "legacy" file system filter driver calls <b>FsRtlRemovePerFileObjectContext </b>to unlink its own per-file-object context structure from the list of per-file-object contexts associated with the file object. All such context structures must have previously been associated with the file object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a>.

If the call to <b>FsRtlRemovePerFileObjectContext </b>is successful, the first per-file-object context structure matching <i>OwnerId</i> (and <i>InstanceId</i>, if present) is unlinked and a pointer to it returned. This pointer can be used by the filter driver to free the unlinked context structure.

<div class="alert"><b>Note</b>  <b>FsRtlRemovePerFileObjectContext </b>unlinks only the first matching per-file-object context structure that is found. If there are additional matching per-file-object contexts, the filter driver must call <b>FsRtlRemovePerFileObjectContext </b>as many times as required to unlink them all.</div>
<div> </div>
To initialize a per-file-object context structure, use the <a href="https://msdn.microsoft.com/8ed219c8-927e-47b1-8ebf-689535dea0fc">FsRtlInitPerFileObjectContext </a>macro.

To associate an initialized per-file-object context structure with a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a> function.

To retrieve a per-file-object context structure that is associated with a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a> function.

<div class="alert"><b>Note</b>    Legacy filter drivers must call the <b>FsRtlRemovePerFileObjectContext</b> function to unlink and free the context information structure before completion of IRP_MJ_CLOSE. Otherwise, the memory allocated to that context structure will be leaked.</div>
<div> </div>
Additionally, file system minifilter drivers must not use the <b>FsRtl</b><i>Xxx</i><b>PerFileObjectContext</b> functions. Instead, they can use the appropriate <b>Flt</b><i>Xxx</i><b>Context</b> functions. For additional information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547346">FSRTL_PER_FILEOBJECT_CONTEXT</a> topic.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547346">FSRTL_PER_FILEOBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a>
 

 

