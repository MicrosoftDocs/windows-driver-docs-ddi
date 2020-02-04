---
UID: NF:ntifs.FsRtlGetNextLargeMcbEntry~r4
title: FsRtlGetNextLargeMcbEntry function (ntifs.h)
description: The FsRtlGetNextLargeMcbEntry routine retrieves a mapping run from a map control block (MCB).
old-location: ifsk\fsrtlgetnextlargemcbentry.htm
tech.root: ifsk
ms.assetid: e67f60da-4200-4d87-9b36-55ce027f0933
ms.date: 03/29/2018
ms.keywords: FsRtlGetNextLargeMcbEntry, FsRtlGetNextLargeMcbEntry routine [Installable File System Drivers], fsrtlref_cee90943-5308-4e1f-ae2e-2e607f19252f.xml, ifsk.fsrtlgetnextlargemcbentry, ntifs/FsRtlGetNextLargeMcbEntry
f1_keywords:
 - "ntifs/FsRtlGetNextLargeMcbEntry"
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
- FsRtlGetNextLargeMcbEntry
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetNextLargeMcbEntry function


## -description


The <b>FsRtlGetNextLargeMcbEntry</b> routine retrieves a mapping run from a map control block (MCB).


## -parameters




### -param Mcb

<p>Pointer to an initialized MCB structure. </p>


### -param RunIndex [in]

Zero-based index of the requested mapping run.


### -param Vbn

<p>Pointer to a variable that receives the starting virtual block number (VBN) of the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.</p>


### -param Lbn

<p>Pointer to a variable that receives the starting logical block number (LBN) of the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.</p>


### -param SectorCount

<p>Pointer to a variable that receives the number of sectors in the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.</p>




## -returns



<b>FsRtlGetNextLargeMcbEntry</b> returns <b>TRUE</b> if the requested mapping run exists in the MCB, <b>FALSE</b> otherwise.




## -remarks



<b>FsRtlGetNextLargeMcbEntry</b> retrieves the starting VBN, starting LBN, and sector count for a mapping run in an MCB.

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>
Holes are counted as runs.

The following code snippet shows how to print out all of the runs in a file:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>for (i = 0; FsRtlGetNextLargeMcbEntry(Mcb,i,&Vbn,&Lbn,&Count); i++) {

    // print out vbn, lbn, and count

}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookuplargemcbentry">FsRtlLookupLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
 

 

