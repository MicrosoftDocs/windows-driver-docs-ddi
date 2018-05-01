---
UID: NF:fltkernel.FltApplyPriorityInfoThread
title: FltApplyPriorityInfoThread function
author: windows-driver-content
description: The FltApplyPriorityInfoThread routine is used by a minifilter driver to apply priority information to a thread.
old-location: ifsk\fltapplypriorityinfothread.htm
old-project: ifsk
ms.assetid: 62fd46a8-ee34-4c61-8e87-7fbe1a4622be
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_446351ed-afa7-4548-8197-f9bf92d671e5.xml, FltApplyPriorityInfoThread, FltApplyPriorityInfoThread routine [Installable File System Drivers], fltkernel/FltApplyPriorityInfoThread, ifsk.fltapplypriorityinfothread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Vista and later versions of Windows operating systems.
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
req.lib: Fltmgr.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Fltmgr.lib
-	Fltmgr.dll
api_name:
-	FltApplyPriorityInfoThread
product: Windows
targetos: Windows
req.typenames: 
---

# FltApplyPriorityInfoThread function


## -description


The <b>FltApplyPriorityInfoThread</b> routine is used by a minifilter driver to apply priority information to a thread.


## -parameters




### -param InputPriorityInfo [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a> structure that is used to set the priority state of the given thread.  This IO_PRIORITY_INFO structure must have its members set by an appropriate routine - see the following Remarks section.  This parameter is required and cannot be <b>NULL</b>.


### -param OutputPriorityInfo [out, optional]

An optional pointer to an IO_PRIORITY_INFO structure used to receive the priority state of the thread before the <i>InputPriorityInfo</i> priority information is applied to the thread by <b>FltApplyPriorityInfoThread</b>.  This parameter is optional and can be <b>NULL</b>.


### -param Thread [in]

A pointer to the thread in which to apply the <i>InputPriorityInfo</i> priority information to.  This parameter is required and cannot be <b>NULL</b>. 


## -returns



If the thread priority information, pointed to by the <i>InputPriorityInfo</i> parameter, is successfully applied to the given thread, the <b>FltApplyPriorityInfoThread</b> routine returns STATUS_SUCCESS.  Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The structure pointed to by the <i>InputPriorityInfo</i> parameter was initialized but one or more of its member values are invalid.  This is an error code.

</td>
</tr>
</table>
 




## -remarks



This routine is available starting with Windows Vista.

The <b>FltApplyPriorityInfoThread</b> routine sets the I/O priority, paging priority and thread priority of the given thread based on the member values of the IO_PRIORITY_INFO structure pointed to by the <i>InputPriorityInfo</i> parameter.  This allows a previously saved set of priority information, acquired by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a> or <b>FltApplyPriorityInfoThread</b> routine, to be applied to a thread.

The original values of the target thread, before the <i>InputPriorityInfo</i> priority values are applied by the <b>FltApplyPriorityInfoThread</b> routine, can be saved if a valid <i>OutputPriorityInfo</i> pointer is supplied.  Note that the structure pointed to by the <i>OutputPriorityInfo</i> parameter need not be initialized.

It is safe to provide the same pointer to a single IO_PRIORITY_INFO structure for both the <i>InputPriorityInfo</i> and <i>OutputPriorityInfo</i> parameters.

<div class="alert"><b>Note</b>    If the member values of the IO_PRIORITY_INFO structure pointed to by the <i>InputPriorityInfo</i> parameter have not been set, you must set these members, prior to calling the <b>FltApplyPriorityInfoThread</b> routine, by using one of the following methods:<ul>
<li>
 Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a> routine.

</li>
<li>
 Ensure that the current <i>InputPriorityInfo</i> parameter was the <i>OutputPriorityInfo</i> parameter in a prior call to the <b>FltApplyPriorityInfoThread</b> routine.

</li>
</ul>
</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543065">FltGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543074">FltGetIoPriorityHintFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543080">FltGetIoPriorityHintFromThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544534">FltSetIoPriorityHintIntoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>
 

 

