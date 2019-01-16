---
UID: NF:ntifs.CcUnpinDataForThread
title: CcUnpinDataForThread function
description: The CcUnpinDataForThread routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to CcSetBcbOwnerPointer.
old-location: ifsk\ccunpindataforthread.htm
tech.root: ifsk
ms.assetid: 9c29689c-ce5e-4b29-a17b-32d96f8f87e7
ms.date: 04/16/2018
ms.keywords: CcUnpinDataForThread, CcUnpinDataForThread routine [Installable File System Drivers], ccref_71102887-ef3b-44b1-8b1f-e2b07dea3392.xml, ifsk.ccunpindataforthread, ntifs/CcUnpinDataForThread
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
-	CcUnpinDataForThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcUnpinDataForThread function


## -description


The <b>CcUnpinDataForThread</b> routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539207">CcSetBcbOwnerPointer</a>.


## -parameters




### -param Bcb [in]

Pointer to the BCB for the pages to be released.


### -param ResourceThreadId [in]

Identifies the thread that originally acquired the BCB. Must match the owner pointer used in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539207">CcSetBcbOwnerPointer</a>.


## -returns



None




## -remarks



<b>CcUnpinDataForThread</b> releases the BCB for the indicated thread and performs any other necessary cleanup.

Each call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539207">CcSetBcbOwnerPointer</a> must be matched by a subsequent call to <b>CcUnpinDataForThread</b>.

<b>CcUnpinDataForThread</b> is functionally equivalent to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>, except that it also releases the BCB resource for the indicated thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539207">CcSetBcbOwnerPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>
 

 

