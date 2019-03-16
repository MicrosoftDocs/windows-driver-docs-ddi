---
UID: NF:ntifs.FsRtlSetupAdvancedHeaderEx
title: FsRtlSetupAdvancedHeaderEx macro (ntifs.h)
description: The FsRtlSetupAdvancedHeaderEx macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with both stream and file contexts.
old-location: ifsk\fsrtlsetupadvancedheaderex.htm
tech.root: ifsk
ms.assetid: 41e5d9f2-ac0b-4834-bca8-88ed872f2f70
ms.date: 04/16/2018
ms.keywords: FsRtlSetupAdvancedHeaderEx, FsRtlSetupAdvancedHeaderEx function [Installable File System Drivers], fsrtlref_9214990b-2568-43d9-801a-c43514a6448f.xml, ifsk.fsrtlsetupadvancedheaderex, ntifs/FsRtlSetupAdvancedHeaderEx
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Update Rollup for Microsoft Windows 2000 Service Pack 4 (SP4) and on Windows XP and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlSetupAdvancedHeaderEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlSetupAdvancedHeaderEx macro


## -description


The <b>FsRtlSetupAdvancedHeaderEx</b> macro is used by file systems to initialize an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with both stream and file contexts.


## -parameters




### -param _advhdr

<p>Pointer to the <a href="https://msdn.microsoft.com/library/Ff547334(v=VS.85).aspx"><b>FSRTL_ADVANCED_FCB_HEADER</b></a> structure to be initialized. </p>


### -param _fmutx

<p>Pointer to an initialized fast mutex that will be used to synchronize access to certain FSRTL_ADVANCED_FCB_HEADER members (for more information, see <a href="https://msdn.microsoft.com/library/Ff547334(v=VS.85).aspx"><b>FSRTL_ADVANCED_FCB_HEADER</b></a>). The fast mutex must be allocated from nonpaged pool. This parameter is optional and can be <b>NULL</b>. Callers should set this parameter to <b>NULL</b> if they intend to use an already existing fast mutex object. If <i>FastMutex</i> is <b>NULL</b>, the caller must explicitly set the <b>FastMutex</b> member of the FSRTL_ADVANCED_FCB_HEADER structure, contained in the stream context object, to point to the existing fast mutex. (This can be done before or after calling <b>FsRtlSetupAdvancedHeaderEx</b>.)</p>


### -param _fctxptr

<p>A pointer to a pointer field used by the file system runtime library (FSRTL) package to track file contexts. </p>
  <p>This parameter is optional and can be <b>NULL</b>.  In particular:</p>
  <ul>
    <li>
      <p> For Microsoft Windows operating systems released prior to Windows Vista: Callers must set this parameter to <b>NULL</b>.</p>
    </li>
    <li>
      <p> For Windows operating systems starting with Windows Vista: If <i>FileContextSupportPointer</i> is not <b>NULL</b>, <i>FileContextSupportPointer</i> must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure.  To indicate that the file system driver does not support file contexts, callers must set <i>FileContextSupportPointer</i> to <b>NULL</b>.</p>
    </li>
  </ul>






## -remarks



File systems use the <b>FsRtlSetupAdvancedHeaderEx</b> macro to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with stream and file contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a> to free all associated stream and file context structures.

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546945">FsRtlLookupPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>
 

 

