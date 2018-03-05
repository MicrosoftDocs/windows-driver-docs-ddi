---
UID: NF:fltkernel.FltIsIoRedirectionAllowedForOperation
title: FltIsIoRedirectionAllowedForOperation function
author: windows-driver-content
description: The FltIsIoRedirectionAllowedForOperation routine determines whether I/O can be redirected from the filter instance associated with the specified FLT_CALLBACK_DATA structure to the specified filter instance.
old-location: ifsk\fltisioredirectionallowedforoperation.htm
old-project: ifsk
ms.assetid: 601a155d-587f-47fc-960e-d1162eabd4b9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltIsIoRedirectionAllowedForOperation, FltIsIoRedirectionAllowedForOperation routine [Installable File System Drivers], fltkernel/FltIsIoRedirectionAllowedForOperation, ifsk.fltisioredirectionallowedforoperation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltIsIoRedirectionAllowedForOperation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsIoRedirectionAllowedForOperation function


## -description


The <b>FltIsIoRedirectionAllowedForOperation</b> routine determines whether I/O can be redirected from the filter instance associated with the specified <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure to the specified filter instance.


## -syntax


````
NTSTATUS FltIsIoRedirectionAllowedForOperation(
  _In_      PFLT_CALLBACK_DATA   Data,
  _In_      PFLT_INSTANCE        TargetInstance,
  _Out_     PBOOLEAN             RedirectionAllowedThisIo,
  _Out_opt_ PBOOLEAN             RedirectionAllowedAllIo
);
````


## -parameters




### -param Data [in]

An <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure representing the I/O operation.


### -param TargetInstance [in]

A filter instance on the target device stack.


### -param RedirectionAllowedThisIo [out]

A value of <b>TRUE</b> if this I/O can be redirected to the target device stack by changing the filter instance referenced.


### -param RedirectionAllowedAllIo [out, optional]

This optional parameter has a value of <b>TRUE</b> if all I/O to the device stack to which the I/O operation is issued can be redirected to the target device by changing the filter instance referenced,  otherwise <b>FALSE</b>.


## -returns



An NTSTATUS value of STATUS_SUCCESS for success or STATUS_NOT_SUPPORTED if the redirection is not supported.




## -remarks



An I/O operation is associated with a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure. That structure contains a reference to a <b>PFLT_IO_PARAMETER_BLOCK</b> object, which contains a reference to the FLT_INSTANCE of the minifilter associated with the I/O operation.

If <i>RedirectionAllowed</i> is <b>TRUE</b>, the minifilter can redirect I/O by changing that instance to a new target instance.

If <i>RedirectionAllowed</i> is <b>FALSE</b>, the minifilter needs to allocate a new callback data object to issue I/O on the target stack or call <a href="..\fltkernel\nf-fltkernel-fltadjustdevicestacksizeforioredirection.md">FltAdjustDeviceStackSizeForIoRedirection</a> to increase the size of the source device stack.

<div class="alert"><b>Note</b>  Minifilters should not modify the reference to the FLT_INSTANCE before verifying that redirection can be done this way. Use <b>FltIsIoRedirectionAllowedForOperation</b> or <a href="..\fltkernel\nf-fltkernel-fltisioredirectionallowed.md">FltIsIoRedirectionAllowed</a>. </div>
<div> </div>



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltisioredirectionallowed.md">FltIsIoRedirectionAllowed</a>



<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>



<a href="..\fltkernel\nf-fltkernel-fltadjustdevicestacksizeforioredirection.md">FltAdjustDeviceStackSizeForIoRedirection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsIoRedirectionAllowedForOperation routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

