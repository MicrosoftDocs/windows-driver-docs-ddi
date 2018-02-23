---
UID: NF:ntifs.FsRtlInsertPerFileContext
title: FsRtlInsertPerFileContext function
author: windows-driver-content
description: The FsRtlInsertPerFileContext routine associates a FSRTL_PER_FILE_CONTEXT object with a driver-specified context object for a file.
old-location: ifsk\fsrtlinsertperfilecontext.htm
old-project: ifsk
ms.assetid: accc3600-9614-48e0-912d-1e8b324e659f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlInsertPerFileContext, ifsk.fsrtlinsertperfilecontext, ntifs/FsRtlInsertPerFileContext, fsrtlref_570a2352-733f-4b83-8f63-f4bfed0e2f56.xml, FsRtlInsertPerFileContext routine [Installable File System Drivers]
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
-	FsRtlInsertPerFileContext
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlInsertPerFileContext function


## -description


The <b>FsRtlInsertPerFileContext</b> routine associates a <a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a> object with a driver-specified context object for a file.


## -syntax


````
NTSTATUS FsRtlInsertPerFileContext(
  _In_ PVOID                   *PerFileContextPointer,
  _In_ PFSRTL_PER_FILE_CONTEXT Ptr
);
````


## -parameters




### -param PerFileContextPointer [in]

A pointer to an opaque pointer used by the file system runtime library (FSRTL) package to track file contexts. To retrieve this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546051">FsRtlGetPerFileContextPointer</a> macro.


### -param Ptr [in]

A pointer to the driver-specific context structure. 


## -returns



The <b>FsRtlInsertPerFileContext</b> routine returns STATUS_SUCCESS, or an appropriate error code, such as:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The underlying file system does not support filter file contexts. You can use the <a href="..\ntifs\nf-ntifs-fsrtlsupportsperfilecontexts.md">FsRtlSupportsPerFileContexts</a> macro to check whether a file system supports per file context objects.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system could not allocate resources (typically memory).

</td>
</tr>
</table>
 




## -remarks



The FsRtlGetPerFileContextPointer macro returns a <i>FileContextSupportPointer</i> for an open file. 

Parameters

<i>FileObject</i>

<b>FILE_OBJECT</b>

A pointer to a file object.

Return value

<b>PVOID</b>

The FsRtlGetPerFileContextPointer macro returns an opaque pointer used by the file system runtime library (FSRTL) package to track file contexts. The macro returns <b>NULL</b> if the file system does not support the use of per-file context objects with files.

The FsRtlGetPerFileContextPointer macro returns the pointer to be passed to routines such as <b>FsRtlInsertPerFileContext</b>, <a href="..\ntifs\nf-ntifs-fsrtllookupperfilecontext.md">FsRtlLookupPerFileContext</a>, and  <a href="..\ntifs\nf-ntifs-fsrtlremoveperfilecontext.md">FsRtlRemovePerFileContext</a>.

For more information about how to use and create context objects, see <a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtllookupperfilecontext.md">FsRtlLookupPerFileContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperfilecontext.md">FsRtlRemovePerFileContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_file_context.md">FSRTL_PER_FILE_CONTEXT</a>



<a href="https://msdn.microsoft.com/6be3ff10-47e4-47f5-8f15-88a80a16f451">Tracking Per-File Context in a Legacy File System Filter Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInsertPerFileContext routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

