---
UID: NF:fltkernel.FltIsIoRedirectionAllowed
title: FltIsIoRedirectionAllowed function
author: windows-driver-content
description: The FltIsIoRedirectionAllowed routine determines whether I/O can be redirected from the specified source filter instance to another specified filter instance.
old-location: ifsk\fltisioredirectionallowed.htm
old-project: ifsk
ms.assetid: 79a59e86-9ee2-4cfa-b495-5248f227d24b
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltIsIoRedirectionAllowed, ifsk.fltisioredirectionallowed, fltkernel/FltIsIoRedirectionAllowed, FltIsIoRedirectionAllowed routine [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltIsIoRedirectionAllowed
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsIoRedirectionAllowed function


## -description


The <b>FltIsIoRedirectionAllowed</b> routine determines whether I/O can be redirected from the specified source filter instance to another specified filter instance.


## -syntax


````
NTSTATUS FltIsIoRedirectionAllowed(
  _In_  PFLT_INSTANCE SourceInstance,
  _In_  PFLT_INSTANCE TargetInstance,
  _Out_ PBOOLEAN      RedirectionAllowed
);
````


## -parameters




### -param SourceInstance [in]

The filter instance on the source device stack.


### -param TargetInstance [in]

The filter instance on the target device stack.


### -param RedirectionAllowed [out]

A value of <b>TRUE</b> if all I/O to the source device stack can be redirected to the target device stack by changing the filter instance referenced, otherwise <b>FALSE</b>.


## -returns



An NTSTATUS value of STATUS_SUCCESS for success or STATUS_NOT_SUPPORTED if redirection is not supported.




## -remarks



An I/O operation is associated with a <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure. That structure contains a reference to a <b>PFLT_IO_PARAMETER_BLOCK</b> object, which contains a reference to the FLT_INSTANCE of the minifilter associated with the I/O operation. 

If <i>RedirectionAllowed</i> is <b>TRUE</b>, the minifilter can redirect I/O by changing that instance to a new target instance.

If <i>RedirectionAllowed</i> is <b>FALSE</b>, the minifilter needs to allocate a new callback data object to issue I/O on the target stack or call <a href="..\fltkernel\nf-fltkernel-fltadjustdevicestacksizeforioredirection.md">FltAdjustDeviceStackSizeForIoRedirection</a> to increase the size of the source device stack.

<div class="alert"><b>Note</b>  Minifilters should not modify the reference to the FLT_INSTANCE before verifying that redirection can be done this way. Use <a href="..\fltkernel\nf-fltkernel-fltisioredirectionallowedforoperation.md">FltIsIoRedirectionAllowedForOperation</a> or <b>FltIsIoRedirectionAllowed</b>. </div>
<div> </div>



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>



<a href="..\fltkernel\nf-fltkernel-fltadjustdevicestacksizeforioredirection.md">FltAdjustDeviceStackSizeForIoRedirection</a>



<a href="..\fltkernel\nf-fltkernel-fltisioredirectionallowedforoperation.md">FltIsIoRedirectionAllowedForOperation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsIoRedirectionAllowed routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

