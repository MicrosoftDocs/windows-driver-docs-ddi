---
UID: NF:ntifs.FsRtlInsertPerStreamContext
title: FsRtlInsertPerStreamContext function
author: windows-driver-content
description: The FsRtlInsertPerStreamContext routine associates a file system filter driver's per-stream context structure with a file stream.
old-location: ifsk\fsrtlinsertperstreamcontext.htm
old-project: ifsk
ms.assetid: d1592021-7765-4553-bcb0-9124af44123f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlInsertPerStreamContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlInsertPerStreamContext
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# FsRtlInsertPerStreamContext function



## -description
The <b>FsRtlInsertPerStreamContext</b> routine associates a file system filter driver's per-stream context structure with a file stream. 



## -syntax

````
NTSTATUS FsRtlInsertPerStreamContext(
  _In_ PFSRTL_ADVANCED_FCB_HEADER StreamContext,
  _In_ PFSRTL_PER_STREAM_CONTEXT  Ptr
);
````


## -parameters

### -param StreamContext [in]

Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro. 


### -param Ptr [in]

Pointer to a FSRTL_PER_STREAM_CONTEXT structure that the filter driver has allocated and initialized. To initialize this structure, use the <a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a> macro. 


## -returns
<b>FsRtlInsertPerStreamContext</b> returns one of the following NTSTATUS values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The call to <b>FsRtlInsertPerStreamContext</b> was successful. 
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The underlying file system does not support filter contexts.

 


## -remarks
A file system filter driver calls <b>FsRtlInsertPerStreamContext</b> to associate its own per-stream context structure with a file stream. The per-stream context structure contains context information that the filter driver maintains for the file stream. 

After the per-stream context structure has been associated with a file stream, it can be retrieved by calling <a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a> or removed by calling <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInsertPerStreamContext routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

