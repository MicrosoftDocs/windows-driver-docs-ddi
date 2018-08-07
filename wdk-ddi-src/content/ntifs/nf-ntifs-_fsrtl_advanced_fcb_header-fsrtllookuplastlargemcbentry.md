---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlLookupLastLargeMcbEntry
title: FsRtlLookupLastLargeMcbEntry function
author: windows-driver-content
description: The FsRtlLookupLastLargeMcbEntry routine retrieves the last mapping entry stored in the map control block (MCB).
old-location: ifsk\fsrtllookuplastlargemcbentry.htm
tech.root: ifsk
ms.assetid: c12a5b96-2e11-45c6-aebf-ee49ac911fa0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlLookupLastLargeMcbEntry, FsRtlLookupLastLargeMcbEntry routine [Installable File System Drivers], fsrtlref_71f4bede-0097-4707-a30e-d09c540f507f.xml, ifsk.fsrtllookuplastlargemcbentry, ntifs/FsRtlLookupLastLargeMcbEntry
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
-	FsRtlLookupLastLargeMcbEntry
product:
-	Windows
targetos: Windows
req.typenames: 
---

# FsRtlLookupLastLargeMcbEntry function


## -description


The <b>FsRtlLookupLastLargeMcbEntry</b> routine retrieves the last mapping entry stored in the map control block (MCB).


## -parameters




### -param Mcb

TBD


### -param Vbn

TBD


### -param Lbn

TBD




#### - LargeLbn [out]

Pointer to a variable that receives the logical block number (LBN) that is mapped to the VBN pointed to by <i>LargeVbn</i>, or -1 if no such LBN exists. 


#### - LargeVbn [out]

Pointer to a variable that receives the last virtual block number (VBN) that was mapped.


#### - OpaqueMcb [in]

Pointer to an initialized MCB structure to be searched. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545587">FsRtlAddLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546040">FsRtlGetNextLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546902">FsRtlLookupLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546918">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547078">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547215">FsRtlRemoveLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547269">FsRtlSplitLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547303">FsRtlTruncateLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

