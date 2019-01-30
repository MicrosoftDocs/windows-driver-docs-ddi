---
UID: NF:fltkernel.FltIsIoRedirectionAllowed
title: FltIsIoRedirectionAllowed function (fltkernel.h)
description: The FltIsIoRedirectionAllowed routine determines whether I/O can be redirected from the specified source filter instance to another specified filter instance.
old-location: ifsk\fltisioredirectionallowed.htm
tech.root: ifsk
ms.assetid: 79a59e86-9ee2-4cfa-b495-5248f227d24b
ms.date: 04/16/2018
ms.keywords: FltIsIoRedirectionAllowed, FltIsIoRedirectionAllowed routine [Installable File System Drivers], fltkernel/FltIsIoRedirectionAllowed, ifsk.fltisioredirectionallowed
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
-	FltIsIoRedirectionAllowed
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIsIoRedirectionAllowed function


## -description


The <b>FltIsIoRedirectionAllowed</b> routine determines whether I/O can be redirected from the specified source filter instance to another specified filter instance.


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



An I/O operation is associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure. That structure contains a reference to a <b>PFLT_IO_PARAMETER_BLOCK</b> object, which contains a reference to the FLT_INSTANCE of the minifilter associated with the I/O operation. 

If <i>RedirectionAllowed</i> is <b>TRUE</b>, the minifilter can redirect I/O by changing that instance to a new target instance.

If <i>RedirectionAllowed</i> is <b>FALSE</b>, the minifilter needs to allocate a new callback data object to issue I/O on the target stack or call <a href="https://msdn.microsoft.com/library/windows/hardware/ff625873">FltAdjustDeviceStackSizeForIoRedirection</a> to increase the size of the source device stack.

<div class="alert"><b>Note</b>  Minifilters should not modify the reference to the FLT_INSTANCE before verifying that redirection can be done this way. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff625875">FltIsIoRedirectionAllowedForOperation</a> or <b>FltIsIoRedirectionAllowed</b>. </div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff625873">FltAdjustDeviceStackSizeForIoRedirection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff625875">FltIsIoRedirectionAllowedForOperation</a>
 

 

