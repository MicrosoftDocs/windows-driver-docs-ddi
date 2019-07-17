---
UID: NF:ntifs.FsRtlSetupAdvancedHeader
title: FsRtlSetupAdvancedHeader function (ntifs.h)
description: The FsRtlSetupAdvancedHeader macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with filter contexts.
old-location: ifsk\fsrtlsetupadvancedheader.htm
tech.root: ifsk
ms.assetid: 8bcf7bbf-6c41-4683-9a62-d408b120c7b9
ms.date: 04/16/2018
ms.keywords: FsRtlSetupAdvancedHeader, FsRtlSetupAdvancedHeader function [Installable File System Drivers], fsrtlref_05f86b8b-48c2-4cb4-b09f-8a4dd1b5ed80.xml, ifsk.fsrtlsetupadvancedheader, ntifs/FsRtlSetupAdvancedHeader
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlSetupAdvancedHeader"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlSetupAdvancedHeader
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlSetupAdvancedHeader function


## -description


The <b>FsRtlSetupAdvancedHeader</b> macro is used by file systems to initialize an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with filter contexts. 


## -parameters




### -param AdvHdr

<p>A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header"><b>FSRTL_ADVANCED_FCB_HEADER</b></a> structure to be initialized. </p>


### -param FMutex

<p>A pointer to an initialized fast mutex that will be used to synchronize access to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header"><b>FSRTL_ADVANCED_FCB_HEADER</b></a> structure. The fast mutex must be allocated from nonpaged pool. </p>
  <p>This parameter can be <b>NULL</b>. Callers should set this parameter to <b>NULL</b> if they intend to use an already existing fast mutex object. If <i>FastMutex</i> is <b>NULL</b>, the caller must explicitly set the <i>FastMutex</i> member of the stream context object to point to the existing fast mutex. (This can be done before or after calling <b>FsRtlSetupAdvancedHeader</b>.) </p>




## -returns



None




## -remarks



File systems use the <b>FsRtlSetupAdvancedHeader</b> macro to initialize an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with filter contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a> to free all associated per-stream context structures. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/tracking-per-stream-context-in-a-legacy-file-system-filter-driver">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlgetperstreamcontextpointer">FsRtlGetPerStreamContextPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlinitperstreamcontext">FsRtlInitPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtllookupperstreamcontext">FsRtlLookupPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>



<a href="https://docs.microsoft.com/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>
 

 

