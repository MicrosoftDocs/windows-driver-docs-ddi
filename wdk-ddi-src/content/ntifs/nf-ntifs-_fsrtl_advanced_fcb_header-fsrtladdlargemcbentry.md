---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAddLargeMcbEntry
title: FsRtlAddLargeMcbEntry function (ntifs.h)
description: The FsRtlAddLargeMcbEntry routine adds a new mapping to an existing map control block (MCB).
old-location: ifsk\fsrtladdlargemcbentry.htm
tech.root: ifsk
ms.assetid: 7cab24f3-624f-4fd1-9f33-76042e5f16ed
ms.date: 04/16/2018
ms.keywords: FsRtlAddLargeMcbEntry, FsRtlAddLargeMcbEntry routine [Installable File System Drivers], fsrtlref_de8b7789-cdba-4535-b2b9-bbc29add7fc6.xml, ifsk.fsrtladdlargemcbentry, ntifs/FsRtlAddLargeMcbEntry
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlAddLargeMcbEntry"
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAddLargeMcbEntry
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlAddLargeMcbEntry function


## -description


The <b>FsRtlAddLargeMcbEntry</b> routine adds a new mapping to an existing map control block (MCB). 


## -parameters




### -param Mcb

<p>Pointer to an initialized MCB structure. </p>


### -param Vbn

<p>Starting virtual block number (VBN) of the new mapping run to be added to the MCB. </p>


### -param Lbn

<p>Logical block number (LBN) to which <i>LargeVbn</i> is to be mapped.</p>


### -param SectorCount

<p>Number of sectors in the new mapping run. </p>




## -returns



<b>FsRtlAddLargeMcbEntry</b> returns <b>TRUE</b> if the new mapping was successfully added to the MCB, <b>FALSE</b> otherwise. 




## -remarks



<b>FsRtlAddLargeMcbEntry</b> adds a new mapping to an existing map control block (MCB). File systems use MCB structures to map virtual block numbers (VBN) for a file to the corresponding logical block numbers (LBN) on disk.

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored, but they must be set to zero. Only the lower 32 bits are used. </div>
<div> </div>
If a new mapping run to be added overlaps an existing mapping run, <b>FsRtlAddLargeMcbEntry</b> merges them into a single mapping run. 

If a pool allocation failure occurs, <b>FsRtlAddLargeMcbEntry</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlAddLargeMcbEntry</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To initialize an MCB, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>. To uninitialize an MCB, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

