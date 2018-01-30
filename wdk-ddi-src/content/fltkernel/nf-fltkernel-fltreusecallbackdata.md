---
UID: NF:fltkernel.FltReuseCallbackData
title: FltReuseCallbackData function
author: windows-driver-content
description: The FltReuseCallbackData routine reinitializes a callback data structure so that it can be reused.
old-location: ifsk\fltreusecallbackdata.htm
old-project: ifsk
ms.assetid: c8671ba7-6128-4f0f-b5b1-32ce35e31168
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltreusecallbackdata, FltApiRef_p_to_z_a412f56d-8cee-40de-93fb-1c007fe87c3c.xml, FltReuseCallbackData routine [Installable File System Drivers], FltReuseCallbackData, fltkernel/FltReuseCallbackData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltReuseCallbackData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltReuseCallbackData function


## -description


The <b>FltReuseCallbackData</b> routine reinitializes a callback data structure so that it can be reused. 


## -syntax


````
VOID FltReuseCallbackData(
  _Inout_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in, out]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure to be reused. This structure must have been allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>. This parameter is required and cannot be <b>NULL</b>. 


## -returns


None 



## -remarks


<b>FltReuseCallbackData</b> reinitializes a callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure so that it can be used in a new I/O operation. <b>FltReuseCallbackData</b> does not change the <b>TargetInstance</b> field or the <b>TargetFileObject</b> field of the callback data structure's I/O parameter block. 

The <b>FltReuseCallbackData</b> routine frees any <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> chain associated with the supplied <i>CallbackData</i> object. A pointer to an MDL chain associated with a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> object will be invalid after a call to <b>FltReuseCallbackData</b> for that object.

Using <b>FltReuseCallbackData</b> to reuse a callback data structure is faster than freeing the structure and allocating a new one. 

A minifilter driver should use <b>FltReuseCallbackData</b> only on a callback data structure that the minifilter driver previously allocated with <a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a> and used in a call to <a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a> or <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>. 

If the callback data structure was used for asynchronous I/O, the minifilter driver should not call <b>FltReuseCallbackData</b> until the <i>CallbackRoutine</i> specified in the call to <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a> is called. 

In particular, a minifilter driver should not use this routine for any callback data structures not allocated by the minifilter driver itself. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>

<a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>

<a href="..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md">FltAllocateCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltperformsynchronousio.md">FltPerformSynchronousIo</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltfreecallbackdata.md">FltFreeCallbackData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReuseCallbackData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

