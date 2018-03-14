---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlResetLargeMcb~r1
title: FsRtlResetLargeMcb function
author: windows-driver-content
description: The FsRtlResetLargeMcb routine truncates a map control block (MCB) structure to contain zero mapping pairs. It does not shrink the mapping pairs array.
old-location: ifsk\fsrtlresetlargemcb.htm
old-project: ifsk
ms.assetid: 49134501-165a-4296-b4c6-3f1e7ae9d485
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlResetLargeMcb, FsRtlResetLargeMcb routine [Installable File System Drivers], fsrtlref_947ccacb-eef2-44d8-9b73-1b8aa930cd03.xml, ifsk.fsrtlresetlargemcb, ntifs/FsRtlResetLargeMcb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlResetLargeMcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlResetLargeMcb function


## -description


The <b>FsRtlResetLargeMcb</b> routine truncates a map control block (MCB) structure to contain zero mapping pairs. It does not shrink the mapping pairs array.


## -syntax


````
VOID FsRtlResetLargeMcb(
  _In_ PLARGE_MCB Mcb,
  _In_ BOOLEAN    SelfSynchronized
);
````


## -parameters




### -param Mcb [in]

Pointer to the MCB structure to truncate.


### -param SelfSynchronized [in]

Indicates whether the caller is already synchronized with respect to the MCB.


## -returns



None




## -remarks



<b>FsRtlResetLargeMcb</b> truncates a map control block (MCB) structure. File systems use MCB structures to map virtual block numbers (VBN) for a file to the corresponding logical block numbers (LBN) on disk.

<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div>
<div> </div>
File systems must call <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a> before using any other <b>FsRtl...Mcb...</b> routines on the MCB structure.

If the caller is already synchronized (the <i>SelfSynchronized</i> parameter is set to <b>TRUE</b>), such that no other thread of operation can call an Mcb routine on this MCB during this call, then <b>FsRtlResetLargeMcb</b> just clears out the current mapping pair count. If the <i>SelfSynchronized</i> parameter is set to <b>FALSE</b>, then <b>FsRtlResetLargeMcb</b> will serialize access to the <i>Mcb</i> before clearing the pair count which requires more time. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>



 

 


