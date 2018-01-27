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
ms.keywords: FsRtlGetNextLargeMcbEntry, ntifs/FsRtlGetNextLargeMcbEntry, fsrtlref_cee90943-5308-4e1f-ae2e-2e607f19252f.xml, ifsk.fsrtlgetnextlargemcbentry, FsRtlGetNextLargeMcbEntry routine [Installable File System Drivers]
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
-	FsRtlGetNextLargeMcbEntry
product: Windows
targetos: Windows
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




### -param Mcb

TBD


### -param RunIndex [in]

Zero-based index of the requested mapping run.


### -param Vbn

TBD


### -param Lbn

TBD


### -param SectorCount

TBD



#### - LargeSectorCount [out]

Pointer to a variable that receives the number of sectors in the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.


#### - LargeLbn [out]

Pointer to a variable that receives the starting logical block number (LBN) of the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.


#### - LargeVbn [out]

Pointer to a variable that receives the starting virtual block number (VBN) of the mapping run, or zero if the run does not exist. Its value is meaningless if <b>FsRtlGetNextLargeMcbEntry</b> returns <b>FALSE</b>.


#### - OpaqueMcb [in]

Pointer to an initialized MCB structure. 


## -returns


<b>FsRtlGetNextLargeMcbEntry</b> returns <b>TRUE</b> if the requested mapping run exists in the MCB, <b>FALSE</b> otherwise. 



## -remarks


<b>FsRtlGetNextLargeMcbEntry</b> retrieves the starting VBN, starting LBN, and sector count for a mapping run in an MCB. 
<div class="alert"><b>Note</b>    The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used. </div><div> </div>Holes are counted as runs. 

The following code snippet shows how to print out all of the runs in a file:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>for (i = 0; FsRtlGetNextLargeMcbEntry(Mcb,i,&amp;Vbn,&amp;Lbn,&amp;Count); i++) {

    // print out vbn, lbn, and count

}</pre>
</td>
</tr>
</table></span></div>


## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md">FsRtlLookupLastLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetNextLargeMcbEntry routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

