---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlInitializeLargeMcb~r1
title: FsRtlInitializeLargeMcb function
author: windows-driver-content
description: The FsRtlInitializeLargeMcb routine initializes a map control block (MCB) structure.
old-location: ifsk\fsrtlinitializelargemcb.htm
old-project: ifsk
ms.assetid: 3b4c879e-d685-4ee9-b44a-a37de4a84800
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fsrtlref_298126ca-6c2b-4662-a7ef-2dbc5d1ba361.xml, ntifs/FsRtlInitializeLargeMcb, FsRtlInitializeLargeMcb routine [Installable File System Drivers], FsRtlInitializeLargeMcb, ifsk.fsrtlinitializelargemcb
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	FsRtlInitializeLargeMcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlInitializeLargeMcb function


## -description


The <b>FsRtlInitializeLargeMcb</b> routine initializes a map control block (MCB) structure.


## -syntax


````
VOID FsRtlInitializeLargeMcb(
  _In_ PLARGE_MCB OpaqueMcb,
  _In_ POOL_TYPE  PoolType
);
````


## -parameters




### -param Mcb

TBD


### -param PoolType [in]

Type of pool to use when allocating additional internal storage for the MCB. One of the following:


<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>

<div class="alert"><b>Note</b>    The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. </div><div> </div>

#### - OpaqueMcb [in]

Pointer to a caller-allocated MCB structure to initialize.


## -returns


None



## -remarks


<b>FsRtlInitializeLargeMcb</b> initializes a map control block (MCB) structure. File systems use MCB structures to map virtual block numbers (VBN) for a file to the corresponding logical block numbers (LBN) on disk.
<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div><div> </div>File systems must call <b>FsRtlInitializeLargeMcb</b> before using any other <b>FsRtl...Mcb...</b> routines on the MCB structure.

If a pool allocation failure occurs, <b>FsRtlInitializeLargeMcb</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlInitializeLargeMcb</b> in a <b>try-except</b> or <b>try-finally</b> statement.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitializeLargeMcb routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

