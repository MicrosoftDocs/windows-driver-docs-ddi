---
UID: NF:fltkernel.FltGetIoPriorityHint
title: FltGetIoPriorityHint function (fltkernel.h)
description: The FltGetIoPriorityHint routine is used by a minifilter driver to get IO priority information from Callback Data.
old-location: ifsk\fltgetiopriorityhint.htm
tech.root: ifsk
ms.assetid: 51c2068b-3dde-4e63-985c-51b8f7020948
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_55aba7ac-700d-4cca-9ad1-abf80293041d.xml, FltGetIoPriorityHint, FltGetIoPriorityHint routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHint, ifsk.fltgetiopriorityhint
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows operating systems.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetIoPriorityHint
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetIoPriorityHint function


## -description


The <b>FltGetIoPriorityHint</b> routine is used by a minifilter driver to get IO priority information from Callback Data.


## -parameters




### -param Data [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>.


## -returns



The <b>FltGetIoPriorityHint</b> routine returns an IO priority hint retrieved from a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure.  




## -remarks



The <b>FltGetIoPriorityHint</b> routine retrieves an IO Priority hint from the <i>Data</i><a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure.  This hint will be based on the following fields in the <b>FLT_CALLBACK_DATA</b>:

<ul>
<li>
IRP (optional)  

</li>
<li>
FileObject  

</li>
<li>
Thread  

</li>
</ul>
If these <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> fields do not have an IO priority, the routine returns IoPriorityNormal.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543074">FltGetIoPriorityHintFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543080">FltGetIoPriorityHintFromThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544534">FltSetIoPriorityHintIntoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>
 

 

