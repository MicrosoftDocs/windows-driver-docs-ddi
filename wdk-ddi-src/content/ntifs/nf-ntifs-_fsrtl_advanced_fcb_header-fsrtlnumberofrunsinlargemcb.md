---
UID: NF:ntifs.FsRtlNumberOfRunsInLargeMcb
title: FsRtlNumberOfRunsInLargeMcb function (ntifs.h)
description: The FsRtlNumberOfRunsInLargeMcb routine returns the number of runs in a map control block (MCB).
old-location: ifsk\fsrtlnumberofrunsinlargemcb.htm
tech.root: ifsk
ms.assetid: a0722e8c-224c-4710-8cd1-68f9bd3051db
ms.date: 04/16/2018
keywords: ["FsRtlNumberOfRunsInLargeMcb function"]
ms.keywords: FsRtlNumberOfRunsInLargeMcb, FsRtlNumberOfRunsInLargeMcb routine [Installable File System Drivers], fsrtlref_26b0787d-7f2e-4bfa-a36f-505836d50d2c.xml, ifsk.fsrtlnumberofrunsinlargemcb, ntifs/FsRtlNumberOfRunsInLargeMcb
f1_keywords:
 - "ntifs/FsRtlNumberOfRunsInLargeMcb"
 - "FsRtlNumberOfRunsInLargeMcb"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlNumberOfRunsInLargeMcb
targetos: Windows
req.typenames: 
---

# FsRtlNumberOfRunsInLargeMcb function


## -description


The <b>FsRtlNumberOfRunsInLargeMcb</b> routine returns the number of runs in a map control block (MCB).


## -parameters




### -param Mcb

<p>Supplies the MCB being examined.</p>




## -returns



Returns the number of distinct runs mapped by the input MCB.




## -remarks



<b>FsRtlNumberOfRunsInLargeMcb</b> returns the number of distinct runs mapped by an MCB. 

Runs can be mappings or holes. A <i>mapping</i> is a continuous range of VBNs that is mapped to a corresponding range of logical block numbers (LBN). Mappings cannot overlap. A <i>hole</i> is a continuous range of unmapped VBNs that falls between two mappings. Within the entire range of mapped VBNs, every VBN belongs to exactly one mapping or hole.

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>
<b>FsRtlNumberOfRunsInLargeMcb</b> counts both types of runs. For example, an MCB containing a mapping for only VBNs zero and three will have three runs: one for VBN 0, one for the hole covering VBN 1 and VBN 2, and one for VBN 3.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

