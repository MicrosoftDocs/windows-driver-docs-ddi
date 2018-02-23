---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlLookupLastLargeMcbEntry~r2
title: FsRtlLookupLastLargeMcbEntry function
author: windows-driver-content
description: The FsRtlLookupLastLargeMcbEntry routine retrieves the last mapping entry stored in the map control block (MCB).
old-location: ifsk\fsrtllookuplastlargemcbentry.htm
old-project: ifsk
ms.assetid: c12a5b96-2e11-45c6-aebf-ee49ac911fa0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/FsRtlLookupLastLargeMcbEntry, FsRtlLookupLastLargeMcbEntry, FsRtlLookupLastLargeMcbEntry routine [Installable File System Drivers], ifsk.fsrtllookuplastlargemcbentry, fsrtlref_71f4bede-0097-4707-a30e-d09c540f507f.xml
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
-	FsRtlLookupLastLargeMcbEntry
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlLookupLastLargeMcbEntry function


## -description


The <b>FsRtlLookupLastLargeMcbEntry</b> routine retrieves the last mapping entry stored in the map control block (MCB).


## -syntax


````
BOOLEAN FsRtlLookupLastLargeMcbEntry(
  _In_  PLARGE_MCB OpaqueMcb,
  _Out_ PLONGLONG  LargeVbn,
  _Out_ PLONGLONG  LargeLbn
);
````


## -parameters




### -param Mcb

TBD


### -param Vbn

TBD


### -param Lbn

TBD




#### - OpaqueMcb [in]

Pointer to an initialized MCB structure to be searched. 


#### - LargeVbn [out]

Pointer to a variable that receives the last virtual block number (VBN) that was mapped.


#### - LargeLbn [out]

Pointer to a variable that receives the logical block number (LBN) that is mapped to the VBN pointed to by <i>LargeVbn</i>, or -1 if no such LBN exists. 


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

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md">FsRtlTruncateLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md">FsRtlRemoveLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md">FsRtlNumberOfRunsInLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md">FsRtlUninitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md">FsRtlGetNextLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md">FsRtlAddLargeMcbEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md">FsRtlInitializeLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md">FsRtlSplitLargeMcb</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md">FsRtlLookupLargeMcbEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlLookupLastLargeMcbEntry routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

