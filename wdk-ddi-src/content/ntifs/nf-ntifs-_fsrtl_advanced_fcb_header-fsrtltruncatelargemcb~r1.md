---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlTruncateLargeMcb~r1
title: FsRtlTruncateLargeMcb function
author: windows-driver-content
description: The FsRtlTruncateLargeMcb routine truncates a large map control block (MCB).
old-location: ifsk\fsrtltruncatelargemcb.htm
old-project: ifsk
ms.assetid: 59970380-0cf5-4557-aa39-854c837552a5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlTruncateLargeMcb, FsRtlTruncateLargeMcb routine [Installable File System Drivers], fsrtlref_5399ea6f-c059-44a7-84f0-01a7eba2c40a.xml, ifsk.fsrtltruncatelargemcb, ntifs/FsRtlTruncateLargeMcb
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
-	FsRtlTruncateLargeMcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlTruncateLargeMcb function


## -description


The <b>FsRtlTruncateLargeMcb</b> routine truncates a large map control block (MCB).


## -syntax


````
VOID FsRtlTruncateLargeMcb(
  _In_ PLARGE_MCB OpaqueMcb,
  _In_ LONGLONG   LargeVbn
);
````


## -parameters




### -param Mcb

TBD


### -param Vbn

TBD




#### - LargeVbn [in]

Starting virtual block number (VBN) of the range of mappings to be removed from the MCB. 


#### - OpaqueMcb [in]

Pointer to the MCB structure. 


## -returns



None




## -remarks



<b>FsRtlTruncateLargeMcb</b> truncates an MCB structure by removing all mappings for VBNs in the range starting with <i>*LargeVbn</i> and ending with the highest mapped VBN. If the starting VBN belongs to a hole (a range of unmapped VBNs that form a gap between two mappings), the hole is also removed. The MCB's <b>PairCount</b> member is adjusted accordingly.

If the starting VBN is zero, all mappings are removed from the MCB. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>



 

 


