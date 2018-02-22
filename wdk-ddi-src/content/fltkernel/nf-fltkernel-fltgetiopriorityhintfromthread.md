---
UID: NF:fltkernel.FltGetIoPriorityHintFromThread
title: FltGetIoPriorityHintFromThread function
author: windows-driver-content
description: The FltGetIoPriorityHintFromThread routine is used by a minifilter driver to get IO priority information from a thread.
old-location: ifsk\fltgetiopriorityhintfromthread.htm
old-project: ifsk
ms.assetid: e79f7cf2-8d3e-42b9-810b-068afa60fb6e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fltgetiopriorityhintfromthread, FltGetIoPriorityHintFromThread, FltGetIoPriorityHintFromThread routine [Installable File System Drivers], FltApiRef_e_to_o_edc8f8c5-8be8-45a7-9936-c2146e5fd4b6.xml, fltkernel/FltGetIoPriorityHintFromThread
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetIoPriorityHintFromThread
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetIoPriorityHintFromThread function


## -description


The <b>FltGetIoPriorityHintFromThread</b> routine is used by a minifilter driver to get IO priority information from a thread.


## -syntax


````
IO_PRIORITY_HINT FltGetIoPriorityHintFromThread(
  _In_ PETHREAD Thread
);
````


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

<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>



<a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetIoPriorityHintFromThread routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

