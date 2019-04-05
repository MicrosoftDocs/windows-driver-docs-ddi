---
UID: NF:ntifs.FsRtlInsertPerStreamContext
title: FsRtlInsertPerStreamContext function (ntifs.h)
description: The FsRtlInsertPerStreamContext routine associates a file system filter driver's per-stream context structure with a file stream.
old-location: ifsk\fsrtlinsertperstreamcontext.htm
tech.root: ifsk
ms.assetid: d1592021-7765-4553-bcb0-9124af44123f
ms.date: 04/16/2018
ms.keywords: FsRtlInsertPerStreamContext, FsRtlInsertPerStreamContext routine [Installable File System Drivers], fsrtlref_91ced881-cdb2-41ca-b569-992d6b43e2f4.xml, ifsk.fsrtlinsertperstreamcontext, ntifs/FsRtlInsertPerStreamContext
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlInsertPerStreamContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlInsertPerStreamContext function


## -description


The <b>FsRtlInsertPerStreamContext</b> routine associates a file system filter driver's per-stream context structure with a file stream. 


## -parameters




### -param PerStreamContext

<p>Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/Ff546056(v=VS.85).aspx"><b>FsRtlGetPerStreamContextPointer</b></a> macro. </p>


### -param Ptr [in]

Pointer to a FSRTL_PER_STREAM_CONTEXT structure that the filter driver has allocated and initialized. To initialize this structure, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a> macro. 


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

After the per-stream context structure has been associated with a file stream, it can be retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546945">FsRtlLookupPerStreamContext</a> or removed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546945">FsRtlLookupPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547257">FsRtlSetupAdvancedHeader</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>
 

 

