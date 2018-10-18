---
UID: NF:fltkernel.FltGetIoPriorityHintFromFileObject
title: FltGetIoPriorityHintFromFileObject function
author: windows-driver-content
description: The FltGetIoPriorityHintFromFileObject routine is used by a minifilter driver to get IO priority information from a file object.
old-location: ifsk\fltgetiopriorityhintfromfileobject.htm
tech.root: ifsk
ms.assetid: ca854716-8f6e-42bd-ae03-e31f951b0874
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_0a239f34-f16d-4386-a171-66c537e3f241.xml, FltGetIoPriorityHintFromFileObject, FltGetIoPriorityHintFromFileObject routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHintFromFileObject, ifsk.fltgetiopriorityhintfromfileobject
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
-	FltGetIoPriorityHintFromFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetIoPriorityHintFromFileObject function


## -description


The <b>FltGetIoPriorityHintFromFileObject</b> routine is used by a minifilter driver to get IO priority information from a file object.


## -parameters




### -param FileObject [in]

A pointer to a file object. This parameter is required and cannot be <b>NULL</b>.


## -returns



The <b>FltGetIoPriorityHintFromFileObject</b> routine returns an IO priority hint retrieved from a file object.

If the <i>FileObject</i> does not have a priority, the routine returns IoPriorityNormal.

If an error occurs retrieving the priority, the routine returns IoPriorityNormal.




## -remarks



This routine is NONPAGED and can be called from paging IO paths.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543065">FltGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543080">FltGetIoPriorityHintFromThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544534">FltSetIoPriorityHintIntoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>
 

 

