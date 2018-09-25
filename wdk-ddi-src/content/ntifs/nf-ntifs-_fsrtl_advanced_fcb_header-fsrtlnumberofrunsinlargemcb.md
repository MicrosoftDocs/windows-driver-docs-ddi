---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNumberOfRunsInLargeMcb
title: FsRtlNumberOfRunsInLargeMcb function
author: windows-driver-content
description: The FsRtlNumberOfRunsInLargeMcb routine returns the number of runs in a map control block (MCB).
old-location: ifsk\fsrtlnumberofrunsinlargemcb.htm
tech.root: ifsk
ms.assetid: a0722e8c-224c-4710-8cd1-68f9bd3051db
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlNumberOfRunsInLargeMcb, FsRtlNumberOfRunsInLargeMcb routine [Installable File System Drivers], fsrtlref_26b0787d-7f2e-4bfa-a36f-505836d50d2c.xml, ifsk.fsrtlnumberofrunsinlargemcb, ntifs/FsRtlNumberOfRunsInLargeMcb
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FsRtlNumberOfRunsInLargeMcb
product:
- Windows
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545587">FsRtlAddLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546040">FsRtlGetNextLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546902">FsRtlLookupLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546910">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546918">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547215">FsRtlRemoveLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547269">FsRtlSplitLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547303">FsRtlTruncateLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

