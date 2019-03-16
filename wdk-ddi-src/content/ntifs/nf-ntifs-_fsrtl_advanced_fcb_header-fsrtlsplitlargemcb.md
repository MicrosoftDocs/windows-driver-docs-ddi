---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlSplitLargeMcb
title: FsRtlSplitLargeMcb function (ntifs.h)
description: The FsRtlSplitLargeMcb routine inserts a hole into the mappings in a map control block (MCB).
old-location: ifsk\fsrtlsplitlargemcb.htm
tech.root: ifsk
ms.assetid: c48b978e-8519-41c0-b711-013c5ccf4abe
ms.date: 04/16/2018
ms.keywords: FsRtlSplitLargeMcb, FsRtlSplitLargeMcb routine [Installable File System Drivers], fsrtlref_f8b7262b-59e2-442d-9525-faa934101bd8.xml, ifsk.fsrtlsplitlargemcb, ntifs/FsRtlSplitLargeMcb
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlSplitLargeMcb
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlSplitLargeMcb function


## -description


The <b>FsRtlSplitLargeMcb</b> routine inserts a hole into the mappings in a map control block (MCB).


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545587">FsRtlAddLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546040">FsRtlGetNextLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546132">FsRtlInitializeLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546902">FsRtlLookupLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546910">FsRtlLookupLastLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546918">FsRtlLookupLastLargeMcbEntryAndIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547078">FsRtlNumberOfRunsInLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547215">FsRtlRemoveLargeMcbEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547303">FsRtlTruncateLargeMcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547318">FsRtlUninitializeLargeMcb</a>
 

 

