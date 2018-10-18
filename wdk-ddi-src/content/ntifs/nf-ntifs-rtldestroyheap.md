---
UID: NF:ntifs.RtlDestroyHeap
title: RtlDestroyHeap function
author: windows-driver-content
description: The RtlDestroyHeap routine destroys the specified heap object. RtlDestroyHeap decommits and releases all the pages of a private heap object, and it invalidates the handle to the heap.
old-location: ifsk\rtldestroyheap.htm
tech.root: ifsk
ms.assetid: e62855a0-284b-434b-88a4-1f21f1b77cf2
ms.date: 4/16/2018
ms.keywords: RtlDestroyHeap, RtlDestroyHeap routine [Installable File System Drivers], ifsk.rtldestroyheap, ntifs/RtlDestroyHeap, rtlref_c1cb90f1-932d-46ab-badc-d960503def9c.xml
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlDestroyHeap
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlDestroyHeap function


## -description


The <b>RtlDestroyHeap</b> routine destroys the specified heap object. <b>RtlDestroyHeap</b> decommits and releases all the pages of a private heap object, and it invalidates the handle to the heap. 


## -parameters




### -param HeapHandle [in]

Handle for the heap to be destroyed. This parameter is a heap handle returned by <b>RtlCreateHeap</b>. 


## -returns



If the call to <b>RtlDestroyHeap</b> succeeds, the return value is a <b>NULL</b> pointer. 

If the call to <b>RtlDestroyHeap</b> fails, the return value is a handle for the heap. 




## -remarks



Processes can call <b>RtlDestroyHeap</b> without first calling <b>RtlFreeHeap</b> to free memory that was allocated from the heap. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552108">RtlAllocateHeap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552159">RtlCreateHeap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552276">RtlFreeHeap</a>
 

 

