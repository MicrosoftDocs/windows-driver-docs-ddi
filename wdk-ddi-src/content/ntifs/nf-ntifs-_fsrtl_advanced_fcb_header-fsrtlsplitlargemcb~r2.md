---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlSplitLargeMcb~r2
title: FsRtlSplitLargeMcb function
author: windows-driver-content
description: The FsRtlSplitLargeMcb routine inserts a hole into the mappings in a map control block (MCB).
old-location: ifsk\fsrtlsplitlargemcb.htm
old-project: ifsk
ms.assetid: c48b978e-8519-41c0-b711-013c5ccf4abe
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FsRtlSplitLargeMcb, FsRtlSplitLargeMcb routine [Installable File System Drivers], L, M, R, S, a, b, c, e, fsrtlref_f8b7262b-59e2-442d-9525-faa934101bd8.xml, g, i, ifsk.fsrtlsplitlargemcb, l, ntifs/FsRtlSplitLargeMcb, p, r, s, t"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlSplitLargeMcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlSplitLargeMcb function


## -description


The <b>FsRtlSplitLargeMcb</b> routine inserts a hole into the mappings in a map control block (MCB).


## -syntax


````
BOOLEAN FsRtlSplitLargeMcb(
  _In_ PLARGE_MCB Mcb,
  _In_ LONGLONG   Vbn,
  _In_ LONGLONG   Amount
);
````


## -parameters




### -param Mcb [in]

Pointer to the MCB structure. 


### -param Vbn [in]

Starting virtual block number (VBN) of the range of mappings to be shifted upward by <i>Amount</i> to make room for the hole. 


### -param Amount [in]

Number of sectors (VBNs) in the hole to be created. 


## -returns



<b>FsRtlSplitLargeMcb</b> returns <b>TRUE</b> if the hole was successfully created, <b>FALSE</b> otherwise.




## -remarks



A hole is a range of unmapped VBNs that form a gap between two mappings. 

If a pool allocation failure occurs, <b>FsRtlSplitLargeMcb</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlSplitLargeMcb</b> in a <b>try-except</b> or <b>try-finally</b> statement.




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlSplitLargeMcb routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

