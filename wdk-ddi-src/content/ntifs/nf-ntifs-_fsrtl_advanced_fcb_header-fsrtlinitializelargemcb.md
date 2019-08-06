---
UID: NF:ntifs.FsRtlInitializeLargeMcb
title: FsRtlInitializeLargeMcb function (ntifs.h)
description: The FsRtlInitializeLargeMcb routine initializes a map control block (MCB) structure.
old-location: ifsk\fsrtlinitializelargemcb.htm
tech.root: ifsk
ms.assetid: 3b4c879e-d685-4ee9-b44a-a37de4a84800
ms.date: 04/16/2018
ms.keywords: FsRtlInitializeLargeMcb, FsRtlInitializeLargeMcb routine [Installable File System Drivers], fsrtlref_298126ca-6c2b-4662-a7ef-2dbc5d1ba361.xml, ifsk.fsrtlinitializelargemcb, ntifs/FsRtlInitializeLargeMcb
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlInitializeLargeMcb"
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
- FsRtlInitializeLargeMcb
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlInitializeLargeMcb function


## -description


The <b>FsRtlInitializeLargeMcb</b> routine initializes a map control block (MCB) structure.


## -parameters




### -param Mcb

<p>Pointer to a caller-allocated MCB structure to initialize.</p>


### -param PoolType [in]

Type of pool to use when allocating additional internal storage for the MCB. One of the following:


<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>


<div class="alert"><b>Note</b>    The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. </div>
<div> </div>

## -returns



None




## -remarks



<b>FsRtlInitializeLargeMcb</b> initializes a map control block (MCB) structure. File systems use MCB structures to map virtual block numbers (VBN) for a file to the corresponding logical block numbers (LBN) on disk.

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>
File systems must call <b>FsRtlInitializeLargeMcb</b> before using any other <b>FsRtl...Mcb...</b> routines on the MCB structure.

If a pool allocation failure occurs, <b>FsRtlInitializeLargeMcb</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlInitializeLargeMcb</b> in a <b>try-except</b> or <b>try-finally</b> statement.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

