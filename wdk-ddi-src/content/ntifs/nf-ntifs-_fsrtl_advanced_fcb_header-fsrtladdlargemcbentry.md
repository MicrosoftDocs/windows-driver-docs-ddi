---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAddLargeMcbEntry
title: FsRtlAddLargeMcbEntry function
author: windows-driver-content
description: The FsRtlAddLargeMcbEntry routine adds a new mapping to an existing map control block (MCB).
old-location: ifsk\fsrtladdlargemcbentry.htm
tech.root: ifsk
ms.assetid: 7cab24f3-624f-4fd1-9f33-76042e5f16ed
ms.date: 4/16/2018
ms.keywords: FsRtlAddLargeMcbEntry, FsRtlAddLargeMcbEntry routine [Installable File System Drivers], fsrtlref_de8b7789-cdba-4535-b2b9-bbc29add7fc6.xml, ifsk.fsrtladdlargemcbentry, ntifs/FsRtlAddLargeMcbEntry
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlAddLargeMcbEntry
product:
-	Windows
targetos: Windows
req.typenames: 
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

To initialize an MCB, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>. To uninitialize an MCB, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546040">FsRtlGetNextLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546902">FsRtlLookupLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546910">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546918">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547078">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547215">FsRtlRemoveLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547269">FsRtlSplitLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547303">FsRtlTruncateLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

