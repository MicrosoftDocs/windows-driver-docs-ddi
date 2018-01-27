---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNumberOfRunsInLargeMcb
title: FsRtlNumberOfRunsInLargeMcb function
author: windows-driver-content
description: The FsRtlNumberOfRunsInLargeMcb routine returns the number of runs in a map control block (MCB).
old-location: ifsk\fsrtlnumberofrunsinlargemcb.htm
old-project: ifsk
ms.assetid: a0722e8c-224c-4710-8cd1-68f9bd3051db
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlNumberOfRunsInLargeMcb routine [Installable File System Drivers], ntifs/FsRtlNumberOfRunsInLargeMcb, FsRtlNumberOfRunsInLargeMcb, fsrtlref_26b0787d-7f2e-4bfa-a36f-505836d50d2c.xml, ifsk.fsrtlnumberofrunsinlargemcb
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
-	FsRtlNumberOfRunsInLargeMcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNumberOfRunsInLargeMcb function


## -description


The <b>FsRtlNumberOfRunsInLargeMcb</b> routine returns the number of runs in a map control block (MCB).


## -syntax


````
ULONG FsRtlNumberOfRunsInLargeMcb(
  _In_ PLARGE_MCB OpaqueMcb
);
````


## -parameters




### -param Mcb

TBD



#### - OpaqueMcb [in]

Supplies the MCB being examined.


## -returns


Returns the number of distinct runs mapped by the input MCB.



## -remarks


<b>FsRtlNumberOfRunsInLargeMcb</b> returns the number of distinct runs mapped by an MCB. 

Runs can be mappings or holes. A <i>mapping</i> is a continuous range of VBNs that is mapped to a corresponding range of logical block numbers (LBN). Mappings cannot overlap. A <i>hole</i> is a continuous range of unmapped VBNs that falls between two mappings. Within the entire range of mapped VBNs, every VBN belongs to exactly one mapping or hole.
<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div><div> </div><b>FsRtlNumberOfRunsInLargeMcb</b> counts both types of runs. For example, an MCB containing a mapping for only VBNs zero and three will have three runs: one for VBN 0, one for the hole covering VBN 1 and VBN 2, and one for VBN 3.



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlNumberOfRunsInLargeMcb routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

