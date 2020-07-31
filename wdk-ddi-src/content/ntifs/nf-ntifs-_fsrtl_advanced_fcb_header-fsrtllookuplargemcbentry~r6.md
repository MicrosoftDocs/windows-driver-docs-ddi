---
UID: NF:ntifs.FsRtlLookupLargeMcbEntry~r6
title: FsRtlLookupLargeMcbEntry function (ntifs.h)
description: Given a virtual block number (VBN) and a map control block (MCB), the FsRtlLookupLargeMcbEntry routine searches the MCB for mapping information corresponding to the specified VBN.
old-location: ifsk\fsrtllookuplargemcbentry.htm
tech.root: ifsk
ms.assetid: 35c6fefb-6045-4b0e-abe8-f78176ca144a
ms.date: 03/29/2018
keywords: ["FsRtlLookupLargeMcbEntry function"]
ms.keywords: FsRtlLookupLargeMcbEntry, FsRtlLookupLargeMcbEntry routine [Installable File System Drivers], fsrtlref_600ea10a-a948-4169-9877-5a8a603b0426.xml, ifsk.fsrtllookuplargemcbentry, ntifs/FsRtlLookupLargeMcbEntry
f1_keywords:
 - "ntifs/FsRtlLookupLargeMcbEntry"
 - "FsRtlLookupLargeMcbEntry"
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
- FsRtlLookupLargeMcbEntry
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlLookupLargeMcbEntry function


## -description


Given a virtual block number (VBN) and a map control block (MCB), the <b>FsRtlLookupLargeMcbEntry</b> routine searches the MCB for mapping information corresponding to the specified VBN.


## -parameters




### -param Mcb

<p>Pointer to an initialized MCB structure. </p>


### -param Vbn

<p>Pointer to the requested VBN.</p>


### -param Lbn

<p>Pointer to a variable that receives the LBN that is mapped to <i>LargeVbn</i> in the mapping entry, or -1 if no such LBN exists. This parameter is optional and can be <b>NULL</b>. </p>


### -param SectorCountFromLbn

<p>Pointer to a variable that receives the number of sectors that follow <i>LargeVbn</i> in the mapping run. This parameter is optional and can be <b>NULL</b>. </p>


### -param StartingLbn

<p>Pointer to a variable that receives the LBN corresponding to the start of the mapping run, or -1 if no such LBN exists. This parameter is optional and can be <b>NULL</b>. </p>


### -param SectorCountFromStartingLbn

<p>Pointer to a variable that receives the number of sectors in the mapping run. This parameter is optional and can be <b>NULL</b>. </p>


### -param Index [out, optional]

Pointer to a variable that receives the index of the mapping run that contains the VBN. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>FsRtlLookupLargeMcbEntry</b> returns <b>TRUE</b> if the specified VBN is within the range of VBNs that are mapped by the MCB, <b>FALSE</b> otherwise.




## -remarks



<b>FsRtlLookupLargeMcbEntry</b> searches for a mapping entry in the MCB whose run includes the specified VBN.

<ul>
<li>
If such a mapping exists, the lookup operation yields positive values for the corresponding LBN and sector count, and <b>FsRtlLookupLargeMcbEntry</b> returns <b>TRUE</b>.

</li>
<li>
If no such mapping exists, but the specified VBN is lower than the highest VBN mapped by the MCB, this is referred to as a hole in the mapping. In this case, <b>FsRtlLookupLargeMcbEntry</b> still returns <b>TRUE</b>, but the lookup operation yields a value of -1 for the LBN.

</li>
<li>
If the specified VBN is higher than the highest VBN mapped by the MCB, or if the MCB contains no mappings, <b>FsRtlLookupLargeMcbEntry</b> returns <b>FALSE</b>.

</li>
</ul>
<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

