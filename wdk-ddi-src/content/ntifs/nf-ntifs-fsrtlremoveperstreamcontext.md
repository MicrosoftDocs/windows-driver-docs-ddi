---
UID: NF:ntifs.FsRtlRemovePerStreamContext
title: FsRtlRemovePerStreamContext function (ntifs.h)
description: FsRtlRemovePerStreamContext removes a per-stream context structure from the list of per-stream contexts associated with a file stream.
old-location: ifsk\fsrtlremoveperstreamcontext.htm
tech.root: ifsk
ms.assetid: 4b046cfa-8f38-4910-8cb3-125395292bd2
ms.date: 04/16/2018
ms.keywords: FsRtlRemovePerStreamContext, FsRtlRemovePerStreamContext function [Installable File System Drivers], fsrtlref_904bd4dd-c254-4762-8af6-dcc49aaa5c92.xml, ifsk.fsrtlremoveperstreamcontext, ntifs/FsRtlRemovePerStreamContext
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Microsoft Windows XP and later.
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
-	FsRtlRemovePerStreamContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlRemovePerStreamContext function


## -description


<b>FsRtlRemovePerStreamContext</b> removes a per-stream context structure from the list of per-stream contexts associated with a file stream. 


## -parameters




### -param StreamContext [in]

Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a> macro. 


### -param OwnerId [in, optional]

Used to identify context information as belonging to a particular filter driver. 


### -param InstanceId [in, optional]

Used to search for a particular instance of a per-stream context. If not provided, any of the contexts owned by the filter driver is removed and returned. 

If neither the <i>OwnerId</i> nor the <i>InstanceId</i> is provided, any associated per-stream context will be removed and returned.


## -returns



<b>FsRtlRemovePerStreamContext</b> returns a pointer to the per-stream context that is removed. If no match is found, or if the file system does not support filter contexts, <b>FsRtlRemovePerStreamContext</b> returns <b>NULL</b>. 




## -remarks



A file system filter driver calls <b>FsRtlRemovePerStreamContext</b> to remove its own per-stream context structure from the list of per-stream contexts associated with a file stream. 

<div class="alert"><b>Note</b>  <b>FsRtlRemovePerStreamContext</b> removes only the first matching per-stream context structure that is found. If there are additional matching per-stream contexts, the filter driver must call <b>FsRtlRemovePerStreamContext</b> as many times as required to remove them all.</div>
<div> </div>
This routine should only be used when a filter driver needs to discard the context information it has associated with a file stream while the stream is still open. For example, a filter driver might call <b>FsRtlRemovePerStreamContext</b> in the following cases: 

<ul>
<li>
When it receives a request from a user-mode application to stop logging I/O requests on a particular volume. 

</li>
<li>
When it detects that a file or directory has been renamed. 

</li>
</ul>
When a file stream is closed, the file system is responsible for ensuring that all per-stream contexts associated with that stream are removed and freed. To do this, the file system must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a> on the file control block (FCB) or other stream context object for the file stream. <b>FsRtlTeardownPerStreamContexts</b> walks the FilterContexts list, removing each entry and calling its <i>FreeCallback</i> routine. 

Thus, a file system filter driver should not call <b>FsRtlRemovePerStreamContext</b> from within an IRP_MJ_CLOSE or IRP_MJ_PNP dispatch routine. Not only would such a call be unnecessary, but it might also interfere with the file system's call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>. 

<div class="alert"><b>Note</b>    A file system filter driver should not call <b>FsRtlRemovePerStreamContext</b> from within a per-stream context structure's <i>FreeCallback</i> routine. This is because the underlying file system calls the <i>FreeCallback</i> routine after it has already removed the context structure from the FilterContexts list.</div>
<div> </div>
To initialize a per-stream context structure, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a> macro. 

To associate an initialized per-stream context structure with a file stream, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>. 

To retrieve a per-stream context structure that is associated with a file stream, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546945">FsRtlLookupPerStreamContext</a>. 

<b>FsRtlRemovePerStreamContext</b> can only be used on file systems that support filter contexts. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546945">FsRtlLookupPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547257">FsRtlSetupAdvancedHeader</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a>
 

 

