---
UID: NF:fltkernel.FltGetIoPriorityHint
title: FltGetIoPriorityHint function
author: windows-driver-content
description: The FltGetIoPriorityHint routine is used by a minifilter driver to get IO priority information from Callback Data.
old-location: ifsk\fltgetiopriorityhint.htm
old-project: ifsk
ms.assetid: 51c2068b-3dde-4e63-985c-51b8f7020948
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_e_to_o_55aba7ac-700d-4cca-9ad1-abf80293041d.xml, FltGetIoPriorityHint routine [Installable File System Drivers], FltGetIoPriorityHint, ifsk.fltgetiopriorityhint, fltkernel/FltGetIoPriorityHint
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetIoPriorityHint
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetIoPriorityHint function


## -description


The <b>FltGetIoPriorityHint</b> routine is used by a minifilter driver to get IO priority information from Callback Data.


## -syntax


````
IO_PRIORITY_HINT FltGetIoPriorityHint(
  _In_ PFLT_CALLBACK_DATA Data
);
````


## -parameters




#### - Data [in]

A pointer to a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>.


## -returns


The <b>FltGetIoPriorityHint</b> routine returns an IO priority hint retrieved from a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure.  



## -remarks


The <b>FltGetIoPriorityHint</b> routine retrieves an IO Priority hint from the <i>Data</i><a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure.  This hint will be based on the following fields in the <b>FLT_CALLBACK_DATA</b>:
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
</ul>If these <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> fields do not have an IO priority, the routine returns IoPriorityNormal.



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>

<a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a>

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>

<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>

<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetIoPriorityHint routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

