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
File systems must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a> before using any other <b>FsRtl...Mcb...</b> routines on the MCB structure.

If the caller is already synchronized (the <i>SelfSynchronized</i> parameter is set to <b>TRUE</b>), such that no other thread of operation can call an Mcb routine on this MCB during this call, then <b>FsRtlResetLargeMcb</b> just clears out the current mapping pair count. If the <i>SelfSynchronized</i> parameter is set to <b>FALSE</b>, then <b>FsRtlResetLargeMcb</b> will serialize access to the <i>Mcb</i> before clearing the pair count which requires more time. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545587">FsRtlAddLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546040">FsRtlGetNextLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546902">FsRtlLookupLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546910">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546918">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547078">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547215">FsRtlRemoveLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547269">FsRtlSplitLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547303">FsRtlTruncateLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlResetLargeMcb routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

