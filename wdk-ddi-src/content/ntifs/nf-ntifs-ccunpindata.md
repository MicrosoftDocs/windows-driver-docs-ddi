---
UID: NF:ntifs.CcUnpinData
title: CcUnpinData function
author: windows-driver-content
description: The CcUnpinData routine releases cached file data that was mapped or pinned by an earlier call to CcMapData, CcPinRead, or CcPreparePinWrite.
old-location: ifsk\ccunpindata.htm
old-project: ifsk
ms.assetid: a06bbe25-9841-4aeb-9d51-257dd1472027
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcUnpinData, CcUnpinData routine [Installable File System Drivers], ccref_ba560a38-4d3b-409f-b1ea-19c3a117615e.xml, ifsk.ccunpindata, ntifs/CcUnpinData
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcUnpinData
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcUnpinData function


## -description


The <b>CcUnpinData</b> routine releases cached file data that was mapped or pinned by an earlier call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>.


## -parameters




### -param Bcb [in]

Pointer to a buffer control block (BCB) for the data to be released.


## -returns



None




## -remarks



<b>CcUnpinData</b> frees the BCB and performs any other necessary cleanup.

Every successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a> must be matched by a subsequent call to <b>CcUnpinData</b>. 

BCBs that have been modified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539207">CcSetBcbOwnerPointer</a> cannot be unpinned by calling <b>CcUnpinData</b>. <a href="https://msdn.microsoft.com/library/windows/hardware/ff539231">CcUnpinDataForThread</a> must be called instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539207">CcSetBcbOwnerPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539231">CcUnpinDataForThread</a>
 

 

