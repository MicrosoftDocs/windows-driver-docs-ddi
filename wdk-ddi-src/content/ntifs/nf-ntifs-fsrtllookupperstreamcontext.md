---
UID: NF:ntifs.FsRtlLookupPerStreamContext
title: FsRtlLookupPerStreamContext macro
author: windows-driver-content
description: The FsRtlLookupPerStreamContext macro retrieves a per-stream context structure for a file stream.
old-location: ifsk\fsrtllookupperstreamcontext.htm
tech.root: ifsk
ms.assetid: 8f8c47c3-1917-4252-b812-711ef52d22d7
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlLookupPerStreamContext, FsRtlLookupPerStreamContext function [Installable File System Drivers], fsrtlref_8284a485-5669-4a4f-a2cf-d566b82299fb.xml, ifsk.fsrtllookupperstreamcontext, ntifs/FsRtlLookupPerStreamContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
-	FsRtlLookupPerStreamContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlLookupPerStreamContext macro


## -description


The <b>FsRtlLookupPerStreamContext</b> macro retrieves a per-stream context structure for a file stream. 


## -parameters




### -param _sc

TBD


### -param _oid

TBD


### -param _iid

TBD






#### - InstanceId [in, optional]

Pointer to a filter driver − allocated variable that can be used to distinguish among per-stream context structures created by the same filter driver. The format of this variable is filter driver − specific. 

If <i>OwnerId</i> and <i>InstanceId</i> are both <b>NULL</b>, <b>FsRtlLookupPerStreamContext</b> returns the first per-stream context found. 

If a non-<b>NULL</b> value is supplied for <i>OwnerId</i> and <i>InstanceId</i> is <b>NULL</b>, <b>FsRtlLookupPerStreamContext</b> returns the first per-stream context found whose <b>OwnerId</b> member matches the <i>OwnerId</i> parameter. 


#### - OwnerId [in, optional]

Pointer to a caller-allocated variable that uniquely identifies the owner of the per-stream context structure. The format of this variable is filter driver − specific. Must be non-<b>NULL</b> if a non-<b>NULL</b> value is supplied for <i>InstanceId</i>. 


#### - StreamContext [in]

Pointer to the FSRTL_ADVANCED_FCB_HEADER structure for the file stream. To get this pointer from a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a> macro. 


## -remarks



A file system filter driver calls <b>FsRtlLookupPerStreamContext</b> to retrieve its per-stream context structure for a file stream. The per-stream context structure contains context information that the filter driver maintains for the file stream. 

<div class="alert"><b>Note</b>  <b>FsRtlLookupPerStreamContext</b>  can only be used on file systems that support per-stream contexts.</div>
<div> </div>
To initialize a per-stream context structure, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a> macro. 

To associate an initialized per-stream context structure with a file stream, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>. 

To remove a per-stream context structure that is associated with a file stream, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547257">FsRtlSetupAdvancedHeader</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>
 

 

