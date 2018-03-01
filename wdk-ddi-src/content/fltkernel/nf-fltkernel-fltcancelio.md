---
UID: NF:fltkernel.FltCancelIo
title: FltCancelIo function
author: windows-driver-content
description: The FltCancelIo routine cancels an I/O operation.
old-location: ifsk\fltcancelio.htm
old-project: ifsk
ms.assetid: 30f2345d-6ed8-475f-879a-d3218039fded
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_e539a1bb-9dd4-4e1b-ac10-b5f742923839.xml, FltCancelIo, FltCancelIo routine [Installable File System Drivers], fltkernel/FltCancelIo, ifsk.fltcancelio
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCancelIo
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCancelIo function


## -description


The <b>FltCancelIo</b> routine cancels an I/O operation. 


## -syntax


````
BOOLEAN FltCancelIo(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````


## -parameters




### -param CallbackData [in]

Pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


## -returns



<b>FltCancelIo</b> returns <b>TRUE</b> if the I/O operation was canceled successfully. Otherwise, it returns <b>FALSE</b>. 




## -remarks



A minifilter driver that initiates an I/O operation by calling a routine such as <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a> can cancel the operation by calling <b>FltCancelIo</b>. The operation must be an IRP-based I/O operation, it must not be currently posted to the minifilter driver's own work queue, and it must not have been completed. 

If the IRP has a cancel routine, <b>FltCancelIo</b> sets the IRP's cancel bit and calls the cancel routine. 

If the IRP does not have a cancel routine, and therefore the IRP is not cancelable, <b>FltCancelIo</b> sets the IRP's cancel bit and returns <b>FALSE</b>. The IRP should be canceled at a later time when it becomes cancelable. 

If a minifilter driver that did not initiate the IRP-based I/O operation calls <b>FltCancelIo</b>, the results are unpredictable. For example, the IRP might be completed with a success NTSTATUS code even though its cancel bit was set. 

<b>FltCancelIo</b> returns <b>FALSE</b> if any of the following conditions are true: 

<ul>
<li>
The operation is not an IRP-based I/O operation. 

</li>
<li>
No cancel routine is specified for the I/O operation. 

</li>
<li>
The I/O operation has already been canceled. 

</li>
</ul>
To determine whether a given callback data structure represents an IRP-based I/O operation, use the FLT_IS_IRP_OPERATION macro. 

To specify a cancel routine for an I/O operation, call <a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>. 

To clear a cancel routine that was set for an I/O operation, call <a href="..\fltkernel\nf-fltkernel-fltclearcancelcompletion.md">FltClearCancelCompletion</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltclearcancelcompletion.md">FltClearCancelCompletion</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>



<a href="..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md">FltSetCancelCompletion</a>



<a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCancelIo routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

