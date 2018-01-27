---
UID: NF:fltkernel.FltGetIoPriorityHintFromCallbackData
title: FltGetIoPriorityHintFromCallbackData function
author: windows-driver-content
description: The FltGetIoPriorityHintFromCallbackData routine is used by a minifilter driver to get IO priority information from callback data.
old-location: ifsk\fltgetiopriorityhintfromcallbackdata.htm
old-project: ifsk
ms.assetid: feb3428c-ab18-4bd5-bf8a-81c7aaab0413
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_e_to_o_ce313b29-9c88-47f7-9a7f-a4ad9945ade1.xml, FltGetIoPriorityHintFromCallbackData, FltGetIoPriorityHintFromCallbackData routine [Installable File System Drivers], ifsk.fltgetiopriorityhintfromcallbackdata, fltkernel/FltGetIoPriorityHintFromCallbackData
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	fltmgr.sys
apiname: 
-	FltGetIoPriorityHintFromCallbackData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetIoPriorityHintFromCallbackData function


## -description


The <b>FltGetIoPriorityHintFromCallbackData</b> routine is used by a minifilter driver to get IO priority information from callback data.


## -syntax


````
IO_PRIORITY_HINT FltGetIoPriorityHintFromCallbackData(
  _In_ PFLT_CALLBACK_DATA Data
);
````


## -parameters




### -param Data [in]

A pointer to a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>. 


## -returns


The <b>FltGetIoPriorityHintFromCallbackData</b> routine returns an IO priority hint retrieved from the <i>Data</i><a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure. 

If the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure does not have an IO priority, the routine returns IoPriorityNormal.

If an error occurs retrieving the hint, the routine returns IoPriorityNormal.



## -remarks


This routine is NONPAGED and can be called from paging IO paths.



## -see-also

<a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a>

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>

<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>

<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetIoPriorityHintFromCallbackData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

