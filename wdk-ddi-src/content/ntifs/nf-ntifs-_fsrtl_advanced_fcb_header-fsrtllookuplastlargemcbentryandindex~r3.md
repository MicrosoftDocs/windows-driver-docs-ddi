---
UID: NF:ntifs.FsRtlLookupLastLargeMcbEntryAndIndex~r3
title: FsRtlLookupLastLargeMcbEntryAndIndex function (ntifs.h)
description: The FsRtlLookupLastLargeMcbEntryAndIndex routine retrieves the last mapping entry stored in a given map control block (MCB).
old-location: ifsk\fsrtllookuplastlargemcbentryandindex.htm
tech.root: ifsk
ms.assetid: 53c3109d-16e4-4db4-9c62-27c6d8501707
ms.date: 03/29/2018
keywords: ["FsRtlLookupLastLargeMcbEntryAndIndex function"]
ms.keywords: FsRtlLookupLastLargeMcbEntryAndIndex, FsRtlLookupLastLargeMcbEntryAndIndex routine [Installable File System Drivers], fsrtlref_d7148458-8a3c-4633-8be3-578623ba4d01.xml, ifsk.fsrtllookuplastlargemcbentryandindex, ntifs/FsRtlLookupLastLargeMcbEntryAndIndex
f1_keywords:
 - "ntifs/FsRtlLookupLastLargeMcbEntryAndIndex"
 - "FsRtlLookupLastLargeMcbEntryAndIndex"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
- FsRtlLookupLastLargeMcbEntryAndIndex
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlLookupLastLargeMcbEntryAndIndex function


## -description


The <b>FsRtlLookupLastLargeMcbEntryAndIndex</b> routine retrieves the last mapping entry stored in a given map control block (MCB).


## -parameters




### -param OpaqueMcb 
[in]
Pointer to an initialized MCB structure to be searched.


### -param LargeVbn 
[out]
Pointer to a variable that receives the last virtual block number (VBN) that was mapped.


### -param LargeLbn 
[out]
Pointer to a variable that receives the logical block number (LBN) that is mapped to the VBN pointed to by <i>LargeVbn</i>, or -1 if no such LBN exists.


### -param Index 
[out]
Pointer to a variable that receives the index of the last run in the MCB.


## -returns



<b>FsRtlLookupLastLargeMcbEntryAndIndex </b>returns <b>FALSE</b> if the MCB contains no mapping entries, <b>TRUE</b> otherwise.




## -remarks



<b>FsRtlLookupLastLargeMcbEntryAndIndex </b>searches for the last mapping of the last run in the MCB:

<ul>
<li>
If the MCB contains no mappings, <b>FsRtlLookupLastLargeMcbEntryAndIndex </b>returns <b>FALSE</b>.

</li>
<li>
If the last mapping is a hole, <b>FsRtlLookupLastLargeMcbEntryAndIndex </b>returns <b>TRUE</b>, but the lookup operation yields a value of -1 for the LBN.

</li>
<li>
If the last mapping is not a hole, the lookup operation yields a positive value for the LBN, and <b>FsRtlLookupLastLargeMcbEntryAndIndex </b>returns <b>TRUE</b>.

</li>
</ul>
<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

