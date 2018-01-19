---
UID: NF:fltkernel.FltSetIoPriorityHintIntoCallbackData
title: FltSetIoPriorityHintIntoCallbackData function
author: windows-driver-content
description: The FltSetIoPriorityHintIntoCallbackData routine is used by a minifilter driver to set the I/O priority information in callback data.
old-location: ifsk\fltsetiopriorityhintintocallbackdata.htm
old-project: ifsk
ms.assetid: 25aba58b-654b-4492-9c54-83c53987342a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltSetIoPriorityHintIntoCallbackData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltSetIoPriorityHintIntoCallbackData
req.alt-loc: fltmgr.sys
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
req.typenames: EXpsFontRestriction
---

# FltSetIoPriorityHintIntoCallbackData function



## -description
The <b>FltSetIoPriorityHintIntoCallbackData</b> routine is used by a minifilter driver to set the I/O priority information in callback data.



## -syntax

````
NTSTATUS FltSetIoPriorityHintIntoCallbackData(
  _In_ PFLT_CALLBACK_DATA Data,
  _In_ IO_PRIORITY_HINT   PriorityHint
);
````


## -parameters

### -param Data [in]

A pointer to a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure that represents an I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param PriorityHint [in]

The <a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a> enumeration value to set for the I/O operation in the callback data pointed to by <i>Data</i>.


## -returns
If this is a fast IO operation, the <b>FltSetIoPriorityHintIntoCallbackData</b> routine returns STATUS_SUCCESS.  
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The value of the <i>PriorityHint</i> parameter is invalid. This is an error code. 

 


## -remarks
This routine is NONPAGED and can be called from paging I/O paths.


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetIoPriorityHintIntoCallbackData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

