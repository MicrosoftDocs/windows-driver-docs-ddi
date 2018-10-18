---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlUninitializeLargeMcb
title: FsRtlUninitializeLargeMcb function
author: windows-driver-content
description: The FsRtlUninitializeLargeMcb routine uninitializes a large map-control block (MCB).
old-location: ifsk\fsrtluninitializelargemcb.htm
tech.root: ifsk
ms.assetid: 684a60e5-f8c4-4ab4-bf55-e50469a67265
ms.date: 04/16/2018
ms.keywords: FsRtlUninitializeLargeMcb, FsRtlUninitializeLargeMcb routine [Installable File System Drivers], fsrtlref_6bd92101-b025-4469-8e05-52afbb5cf75e.xml, ifsk.fsrtluninitializelargemcb, ntifs/FsRtlUninitializeLargeMcb
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
-	FsRtlUninitializeLargeMcb
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlUninitializeLargeMcb function


## -description


The <b>FsRtlUninitializeLargeMcb</b> routine uninitializes a large map-control block (MCB).


## -parameters




### -param Mcb

<p>Supplies a pointer to the MCB structure to uninitialize. The MCB must have been initialized by calling <a href="https://msdn.microsoft.com/library/Ff546132(v=VS.85).aspx"><b>FsRtlInitializeLargeMcb</b></a>.</p>




## -returns



None




## -remarks



<b>FsRtlUninitializeLargeMcb</b> uninitializes an MCB structure. 

Once uninitialized, the MCB can be initialized for reuse by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>.




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
 

 

