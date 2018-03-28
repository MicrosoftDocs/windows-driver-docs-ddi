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


## -parameters




### -param Mcb

TBD


### -param Vbn

TBD




#### - OpaqueMcb [in]

Pointer to the MCB structure. 


#### - LargeVbn [in]

Starting virtual block number (VBN) of the range of mappings to be removed from the MCB. 


## -returns



None




## -remarks



<b>FsRtlTruncateLargeMcb</b> truncates an MCB structure by removing all mappings for VBNs in the range starting with <i>*LargeVbn</i> and ending with the highest mapped VBN. If the starting VBN belongs to a hole (a range of unmapped VBNs that form a gap between two mappings), the hole is also removed. The MCB's <b>PairCount</b> member is adjusted accordingly.

If the starting VBN is zero, all mappings are removed from the MCB. 




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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlTruncateLargeMcb routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

