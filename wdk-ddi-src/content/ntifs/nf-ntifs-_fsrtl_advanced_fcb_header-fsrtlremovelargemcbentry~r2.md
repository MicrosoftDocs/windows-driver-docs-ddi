---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlRemoveLargeMcbEntry~r2
title: FsRtlRemoveLargeMcbEntry function
author: windows-driver-content
description: The FsRtlRemoveLargeMcbEntry routine removes one or more mappings from a map control block (MCB).
old-location: ifsk\fsrtlremovelargemcbentry.htm
old-project: ifsk
ms.assetid: c0608442-59ba-4431-94d5-7514555d0b4f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlRemoveLargeMcbEntry, FsRtlRemoveLargeMcbEntry routine [Installable File System Drivers], fsrtlref_d80cc918-81da-4aae-b8ba-b2aea9519af3.xml, ifsk.fsrtlremovelargemcbentry, ntifs/FsRtlRemoveLargeMcbEntry
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
-	FsRtlRemoveLargeMcbEntry
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlRemoveLargeMcbEntry function


## -description


The <b>FsRtlRemoveLargeMcbEntry</b> routine removes one or more mappings from a map control block (MCB).


## -parameters




### -param Mcb

TBD


### -param Vbn

TBD


### -param SectorCount

TBD




#### - OpaqueMcb [in]

Pointer to the MCB structure. 


#### - LargeVbn [in]

Starting virtual block number (VBN) of the range for which mappings are to be removed from the MCB. 


#### - LargeSectorCount [in]

Number of sectors (VBNs) in the range for which mappings are to be removed. 


## -returns



None




## -remarks



<b>FsRtlRemoveLargeMcbEntry</b> removes all mappings of VBNs to LBNs in the MCB that fall within the range of VBNs that begins with <i>*LargeVbn</i> and ends with (<i>*LargeVbn </i>+ <i>LargeSectorCount</i> - 1). 

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>
Holes (gaps) between mappings are ignored. 

If the range of VBNs to be removed includes the highest mapped VBN in the MCB, the MCB's <b>PairCount</b> member is adjusted accordingly.

If a pool allocation failure occurs, <b>FsRtlRemoveLargeMcbEntry</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlRemoveLargeMcbEntry</b> in a <b>try-except</b> or <b>try-finally</b> statement.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545587">FsRtlAddLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546040">FsRtlGetNextLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546902">FsRtlLookupLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546910">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546918">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547078">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547269">FsRtlSplitLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547303">FsRtlTruncateLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlRemoveLargeMcbEntry routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

