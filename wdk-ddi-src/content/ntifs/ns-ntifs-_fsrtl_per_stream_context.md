---
UID: NS:ntifs._FSRTL_PER_STREAM_CONTEXT
title: "_FSRTL_PER_STREAM_CONTEXT"
author: windows-driver-content
description: The FSRTL_PER_STREAM_CONTEXT structure contains context information that a file system filter driver maintains about a file stream.
old-location: ifsk\fsrtl_per_stream_context.htm
old-project: ifsk
ms.assetid: 108c224c-ae42-414f-951d-cb225059d525
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FSRTL_PER_STREAM_CONTEXT structure [Installable File System Drivers], ntifs/PFSRTL_PER_STREAM_CONTEXT, PFSRTL_PER_STREAM_CONTEXT structure pointer [Installable File System Drivers], ntifs/FSRTL_PER_STREAM_CONTEXT, ifsk.fsrtl_per_stream_context, *PFSRTL_PER_STREAM_CONTEXT, contextstructures_c3576880-65f8-4340-b1d2-82d66f8e4f30.xml, PFSRTL_PER_STREAM_CONTEXT, _FSRTL_PER_STREAM_CONTEXT, FSRTL_PER_STREAM_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Microsoft Windows XP and later.
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FSRTL_PER_STREAM_CONTEXT
product: Windows
targetos: Windows
req.typenames: FSRTL_PER_STREAM_CONTEXT, *PFSRTL_PER_STREAM_CONTEXT
---

# _FSRTL_PER_STREAM_CONTEXT structure


## -description


The <b>FSRTL_PER_STREAM_CONTEXT</b> structure contains context information that a file system filter driver maintains about a file stream. 


## -syntax


````
typedef struct _FSRTL_PER_STREAM_CONTEXT {
  LIST_ENTRY     Links;
  PVOID          OwnerId;
  PVOID          InstanceId;
  PFREE_FUNCTION FreeCallback;
} FSRTL_PER_STREAM_CONTEXT, *PFSRTL_PER_STREAM_CONTEXT;
````


## -struct-fields




### -field Links

Link for this structure in the list of all per-stream context structures associated with the same file stream. <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a> inserts this member into the list of all per-stream context structures for a file stream. To get a pointer to the head of the list from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro, and cast the result to a <b>PFSRTL_ADVANCED_FCB_HEADER</b> pointer. The list pointer is the <b>FilterContexts</b> member in the advanced file control block (FCB) header structure for the file stream. 


### -field OwnerId

Pointer to a filter-driver-allocated variable that uniquely identifies the owner of the per-stream context structure. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of a driver object or device object. Filter drivers must set this member to a non-<b>NULL</b> value. 


### -field InstanceId

Pointer to a filter-driver-allocated variable that can be used to distinguish among per-stream context structures created by the same filter driver. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the stream context object for the file stream. (To get this address from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro.) 

This member is optional and can be <b>NULL</b>. 


### -field FreeCallback

Pointer to a callback routine that frees the per-stream context structure. This routine and its parameters are defined as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PFREE_FUNCTION) (
     IN PVOID Buffer
     );</pre>
</td>
</tr>
</table></span></div>




#### Buffer

Pointer to the <b>FSRTL_PER_STREAM_CONTEXT</b> structure to free. 


## -remarks



File system filter drivers can use a <b>FSRTL_PER_STREAM_CONTEXT</b> structure to maintain context information for a file stream. This structure can be used as is or embedded in a driver-defined, per-stream context structure. 

When a file system tears down the stream context object for a file stream, it must call <a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>, which in turn calls the <i>FreeCallback</i> routines of all per-stream context structures associated with the file stream. 

<div class="alert"><b>Note</b>    The <i>FreeCallback</i> routine cannot recursively call down into the file system or acquire any file system resources. Also, this routine must assume that the file object for the file stream has already been freed. </div>
<div> </div>
The <b>FSRTL_PER_STREAM_CONTEXT</b> structure can be allocated from paged or nonpaged pool. 

The <b>FsRtlSupportsPerStreamContexts</b> macro determines whether a file system supports per-stream contexts for a given file stream. 

<pre class="syntax" xml:space="preserve"><code>BOOLEAN FsRtlSupportsPerStreamContexts(
  [in] PFILE_OBJECT FileObject
);
</code></pre>
Parameters

<i>FileObject [in]</i>

<b>PFILE_OBJECT</b>

A pointer to a file object for the file stream.

Return value

<b>BOOLEAN</b>

The <b>FsRtlSupportsPerStreamContexts</b> macro returns <b>TRUE</b> if the file system supports per-stream contexts for the file stream, <b>FALSE</b> otherwise. 

File system filter drivers call <b>FsRtlSupportsPerStreamContexts</b> to determine whether the underlying file system supports per-stream contexts for the file stream represented by a given file object. Note that a file system might support per-stream contexts for some types of files but not for others. For example, NTFS and FAT do not currently support per-stream contexts for paging files. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551123">PFREE_FUNCTION</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_PER_STREAM_CONTEXT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

