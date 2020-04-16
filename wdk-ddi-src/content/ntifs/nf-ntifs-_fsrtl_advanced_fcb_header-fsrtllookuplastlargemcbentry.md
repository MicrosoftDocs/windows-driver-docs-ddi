---
UID: NF:ntifs.FsRtlLookupLastLargeMcbEntry
title: FsRtlLookupLastLargeMcbEntry function (ntifs.h)
description: The FsRtlLookupLastLargeMcbEntry routine retrieves the last mapping entry stored in the map control block (MCB).
old-location: ifsk\fsrtllookuplastlargemcbentry.htm
tech.root: ifsk
ms.assetid: c12a5b96-2e11-45c6-aebf-ee49ac911fa0
ms.date: 04/16/2018
keywords: ["FsRtlLookupLastLargeMcbEntry function"]
ms.keywords: FsRtlLookupLastLargeMcbEntry, FsRtlLookupLastLargeMcbEntry routine [Installable File System Drivers], fsrtlref_71f4bede-0097-4707-a30e-d09c540f507f.xml, ifsk.fsrtllookuplastlargemcbentry, ntifs/FsRtlLookupLastLargeMcbEntry
f1_keywords:
 - "ntifs/FsRtlLookupLastLargeMcbEntry"
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
- FsRtlLookupLastLargeMcbEntry
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlLookupLastLargeMcbEntry function


## -description


The <b>FsRtlLookupLastLargeMcbEntry</b> routine retrieves the last mapping entry stored in the map control block (MCB).


## -parameters




### -param Mcb

<p>Pointer to an initialized MCB structure to be searched. </p>


### -param Vbn

<p>Pointer to a variable that receives the last virtual block number (VBN) that was mapped.</p>


### -param Lbn

<p>Pointer to a variable that receives the logical block number (LBN) that is mapped to the VBN pointed to by <i>LargeVbn</i>, or -1 if no such LBN exists. </p>




## -returns



<b>FsRtlLookupLastLargeMcbEntry</b> returns <b>FALSE</b> if the MCB contains no mapping entries, <b>TRUE</b> otherwise.




## -remarks



<b>FsRtlLookupLastLargeMcbEntry</b> searches for the last mapping of the last run in the MCB: 

<ul>
<li>
If the MCB contains no mappings, <b>FsRtlLookupLastLargeMcbEntry</b> returns <b>FALSE</b>.

</li>
<li>
If the last mapping is a hole, <b>FsRtlLookupLastLargeMcbEntry</b> returns <b>TRUE</b>, but the lookup operation yields a value of -1 for the LBN.

</li>
<li>
If the last mapping is not a hole, the lookup operation yields a positive value for the LBN, and <b>FsRtlLookupLastLargeMcbEntry</b> returns <b>TRUE</b>. 

</li>
</ul>
<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

