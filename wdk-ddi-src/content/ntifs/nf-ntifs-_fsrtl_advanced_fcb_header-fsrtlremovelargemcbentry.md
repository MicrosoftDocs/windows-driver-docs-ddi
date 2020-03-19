---
UID: NF:ntifs.FsRtlRemoveLargeMcbEntry
title: FsRtlRemoveLargeMcbEntry function (ntifs.h)
description: The FsRtlRemoveLargeMcbEntry routine removes one or more mappings from a map control block (MCB).
old-location: ifsk\fsrtlremovelargemcbentry.htm
tech.root: ifsk
ms.assetid: c0608442-59ba-4431-94d5-7514555d0b4f
ms.date: 04/16/2018
keywords: ["FsRtlRemoveLargeMcbEntry function"]
ms.keywords: FsRtlRemoveLargeMcbEntry, FsRtlRemoveLargeMcbEntry routine [Installable File System Drivers], fsrtlref_d80cc918-81da-4aae-b8ba-b2aea9519af3.xml, ifsk.fsrtlremovelargemcbentry, ntifs/FsRtlRemoveLargeMcbEntry
f1_keywords:
 - "ntifs/FsRtlRemoveLargeMcbEntry"
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
- FsRtlRemoveLargeMcbEntry
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlRemoveLargeMcbEntry function


## -description


The <b>FsRtlRemoveLargeMcbEntry</b> routine removes one or more mappings from a map control block (MCB).


## -parameters




### -param Mcb

<p>Pointer to the MCB structure. </p>


### -param Vbn

<p>Starting virtual block number (VBN) of the range for which mappings are to be removed from the MCB. </p>


### -param SectorCount

<p>Number of sectors (VBNs) in the range for which mappings are to be removed. </p>




## -remarks



<b>FsRtlRemoveLargeMcbEntry</b> removes all mappings of VBNs to LBNs in the MCB that fall within the range of VBNs that begins with <i>*LargeVbn</i> and ends with (<i>*LargeVbn </i>+ <i>LargeSectorCount</i> - 1). 

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>
Holes (gaps) between mappings are ignored. 

If the range of VBNs to be removed includes the highest mapped VBN in the MCB, the MCB's <b>PairCount</b> member is adjusted accordingly.

If a pool allocation failure occurs, <b>FsRtlRemoveLargeMcbEntry</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlRemoveLargeMcbEntry</b> in a <b>try-except</b> or <b>try-finally</b> statement.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

