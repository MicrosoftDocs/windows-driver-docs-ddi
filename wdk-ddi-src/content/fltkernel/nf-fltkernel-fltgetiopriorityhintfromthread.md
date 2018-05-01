---
UID: NF:fltkernel.FltGetIoPriorityHintFromThread
title: FltGetIoPriorityHintFromThread function
author: windows-driver-content
description: The FltGetIoPriorityHintFromThread routine is used by a minifilter driver to get IO priority information from a thread.
old-location: ifsk\fltgetiopriorityhintfromthread.htm
old-project: ifsk
ms.assetid: e79f7cf2-8d3e-42b9-810b-068afa60fb6e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_edc8f8c5-8be8-45a7-9936-c2146e5fd4b6.xml, FltGetIoPriorityHintFromThread, FltGetIoPriorityHintFromThread routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHintFromThread, ifsk.fltgetiopriorityhintfromthread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetIoPriorityHintFromThread
product: Windows
targetos: Windows
req.typenames: 
---

# FltGetIoPriorityHintFromThread function


## -description


The <b>FltGetIoPriorityHintFromThread</b> routine is used by a minifilter driver to get IO priority information from a thread.


## -parameters




### -param Thread [in]

A pointer to the thread from which to retrieve priority information. This parameter is required and cannot be <b>NULL</b>. 


## -returns



The <b>FltGetIoPriorityHintFromThread</b> routine returns an IO priority hint retrieved from a thread.

If <i>Thread</i> does not have a priority, the routine returns IoPriorityNormal.




If an error occurs retrieving the priority, the routine returns IoPriorityNormal.




## -remarks



This routine is NONPAGED and can be called from paging IO paths.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543065">FltGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543074">FltGetIoPriorityHintFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544534">FltSetIoPriorityHintIntoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>
 

 

