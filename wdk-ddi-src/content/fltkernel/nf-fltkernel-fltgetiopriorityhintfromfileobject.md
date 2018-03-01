---
UID: NF:fltkernel.FltGetIoPriorityHintFromFileObject
title: FltGetIoPriorityHintFromFileObject function
author: windows-driver-content
description: The FltGetIoPriorityHintFromFileObject routine is used by a minifilter driver to get IO priority information from a file object.
old-location: ifsk\fltgetiopriorityhintfromfileobject.htm
old-project: ifsk
ms.assetid: ca854716-8f6e-42bd-ae03-e31f951b0874
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_0a239f34-f16d-4386-a171-66c537e3f241.xml, FltGetIoPriorityHintFromFileObject, FltGetIoPriorityHintFromFileObject routine [Installable File System Drivers], fltkernel/FltGetIoPriorityHintFromFileObject, ifsk.fltgetiopriorityhintfromfileobject
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
-	FltGetIoPriorityHintFromFileObject
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetIoPriorityHintFromFileObject function


## -description


The <b>FltGetIoPriorityHintFromFileObject</b> routine is used by a minifilter driver to get IO priority information from a file object.


## -syntax


````
IO_PRIORITY_HINT FltGetIoPriorityHintFromFileObject(
  _In_ PFILE_OBJECT FileObject
);
````


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

<a href="..\ntifs\ns-ntifs-_io_priority_info.md">IO_PRIORITY_INFO</a>



<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetIoPriorityHintFromFileObject routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

