---
UID: NF:fltkernel.FltApplyPriorityInfoThread
title: FltApplyPriorityInfoThread function
author: windows-driver-content
description: The FltApplyPriorityInfoThread routine is used by a minifilter driver to apply priority information to a thread.
old-location: ifsk\fltapplypriorityinfothread.htm
old-project: ifsk
ms.assetid: 62fd46a8-ee34-4c61-8e87-7fbe1a4622be
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_446351ed-afa7-4548-8197-f9bf92d671e5.xml, fltkernel/FltApplyPriorityInfoThread, FltApplyPriorityInfoThread routine [Installable File System Drivers], ifsk.fltapplypriorityinfothread, FltApplyPriorityInfoThread
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Fltmgr.lib
-	Fltmgr.dll
apiname:
-	FltApplyPriorityInfoThread
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltApplyPriorityInfoThread function


## -description


The <b>FltApplyPriorityInfoThread</b> routine is used by a minifilter driver to apply priority information to a thread.


## -syntax


````
NTSTATUS FltApplyPriorityInfoThread(
  _In_      PIO_PRIORITY_INFO InputPriorityInfo,
  _Out_opt_ PIO_PRIORITY_INFO OutputPriorityInfo,
  _In_      PETHREAD          Thread
);
````


## -parameters




### -param InputPriorityInfo [in]

A pointer to an <a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a> structure that is used to set the priority state of the given thread.  This IO_PRIORITY_INFO structure must have its members set by an appropriate routine - see the following Remarks section.  This parameter is required and cannot be <b>NULL</b>.


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

The <b>FltApplyPriorityInfoThread</b> routine sets the I/O priority, paging priority and thread priority of the given thread based on the member values of the IO_PRIORITY_INFO structure pointed to by the <i>InputPriorityInfo</i> parameter.  This allows a previously saved set of priority information, acquired by the <a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a> or <b>FltApplyPriorityInfoThread</b> routine, to be applied to a thread.

The original values of the target thread, before the <i>InputPriorityInfo</i> priority values are applied by the <b>FltApplyPriorityInfoThread</b> routine, can be saved if a valid <i>OutputPriorityInfo</i> pointer is supplied.  Note that the structure pointed to by the <i>OutputPriorityInfo</i> parameter need not be initialized.

It is safe to provide the same pointer to a single IO_PRIORITY_INFO structure for both the <i>InputPriorityInfo</i> and <i>OutputPriorityInfo</i> parameters.

<div class="alert"><b>Note</b>    If the member values of the IO_PRIORITY_INFO structure pointed to by the <i>InputPriorityInfo</i> parameter have not been set, you must set these members, prior to calling the <b>FltApplyPriorityInfoThread</b> routine, by using one of the following methods:<ul>
<li>
 Call the <a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a> routine.

</li>
<li>
 Ensure that the current <i>InputPriorityInfo</i> parameter was the <i>OutputPriorityInfo</i> parameter in a prior call to the <b>FltApplyPriorityInfoThread</b> routine.

</li>
</ul>
</div>
<div> </div>



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>



<a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltApplyPriorityInfoThread routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

