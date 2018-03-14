---
UID: NF:ntifs.FsRtlInsertPerStreamContext
title: FsRtlInsertPerStreamContext function
author: windows-driver-content
description: The FsRtlInsertPerStreamContext routine associates a file system filter driver's per-stream context structure with a file stream.
old-location: ifsk\fsrtlinsertperstreamcontext.htm
old-project: ifsk
ms.assetid: d1592021-7765-4553-bcb0-9124af44123f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlInsertPerStreamContext, FsRtlInsertPerStreamContext routine [Installable File System Drivers], fsrtlref_91ced881-cdb2-41ca-b569-992d6b43e2f4.xml, ifsk.fsrtlinsertperstreamcontext, ntifs/FsRtlInsertPerStreamContext
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
-	FsRtlInsertPerStreamContext
product: Windows
targetos: Windows
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




### -param PerStreamContext

TBD


### -param Ptr [in]

Pointer to a FSRTL_PER_STREAM_CONTEXT structure that the filter driver has allocated and initialized. To initialize this structure, use the <a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a> macro. 


#### - StreamContext [in]

Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro. 


## -returns



<b>FsRtlInsertPerStreamContext</b> returns one of the following NTSTATUS values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call to <b>FsRtlInsertPerStreamContext</b> was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The underlying file system does not support filter contexts.

</td>
</tr>
</table>
 




## -remarks



A file system filter driver calls <b>FsRtlInsertPerStreamContext</b> to associate its own per-stream context structure with a file stream. The per-stream context structure contains context information that the filter driver maintains for the file stream. 

After the per-stream context structure has been associated with a file stream, it can be retrieved by calling <a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a> or removed by calling <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>



 

 


