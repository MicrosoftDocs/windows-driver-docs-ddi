---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlGetNextLargeMcbEntry~r4
title: FsRtlGetNextLargeMcbEntry function
author: windows-driver-content
description: The FsRtlGetNextLargeMcbEntry routine retrieves a mapping run from a map control block (MCB).
old-location: ifsk\fsrtlgetnextlargemcbentry.htm
old-project: ifsk
ms.assetid: e67f60da-4200-4d87-9b36-55ce027f0933
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlGetNextLargeMcbEntry
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
req.alt-api: FsRtlGetNextLargeMcbEntry
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# FsRtlGetNextLargeMcbEntry function



## -description
The <b>FsRtlGetNextLargeMcbEntry</b> routine retrieves a mapping run from a map control block (MCB).



## -syntax

````
BOOLEAN FsRtlGetNextLargeMcbEntry(
  _In_  PLARGE_MCB OpaqueMcb,
  _In_  ULONG      RunIndex,
  _Out_ PLONGLONG  LargeVbn,
  _Out_ PLONGLONG  LargeLbn,
  _Out_ PLONGLONG  LargeSectorCount
);
````


## -parameters

### -param OpaqueMcb [in]

Pointer to an initialized MCB structure. 


### -param RunIndex [in]

Zero-based index of the requested mapping run.


### -param LargeVbn [out]

Pointer to a variable that receives the starting virtual block number (VBN) of the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.


### -param LargeLbn [out]

Pointer to a variable that receives the starting logical block number (LBN) of the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.


### -param LargeSectorCount [out]

Pointer to a variable that receives the number of sectors in the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.


## -returns
<b>FsRtlGetNextLargeMcbEntry</b> returns <b>TRUE</b> if the requested mapping run exists in the MCB, <b>FALSE</b> otherwise. 


## -remarks
<b>FsRtlGetNextLargeMcbEntry</b> retrieves the starting VBN, starting LBN, and sector count for a mapping run in an MCB. 

Holes are counted as runs. 

The following code snippet shows how to print out all of the runs in a file:


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetNextLargeMcbEntry routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

