---
UID: NF:fltkernel.FltIsIoRedirectionAllowedForOperation
title: FltIsIoRedirectionAllowedForOperation function
author: windows-driver-content
description: The FltIsIoRedirectionAllowedForOperation routine determines whether I/O can be redirected from the filter instance associated with the specified FLT_CALLBACK_DATA structure to the specified filter instance.
old-location: ifsk\fltisioredirectionallowedforoperation.htm
old-project: ifsk
ms.assetid: 601a155d-587f-47fc-960e-d1162eabd4b9
ms.author: windowsdriverdev
ms.date: 4/16/2018
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIsIoRedirectionAllowedForOperation function


## -description


The <b>FltIsIoRedirectionAllowedForOperation</b> routine determines whether I/O can be redirected from the filter instance associated with the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure to the specified filter instance.


## -parameters




### -param Data [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure representing the I/O operation.


### -param TargetInstance [in]

A filter instance on the target device stack.


### -param RedirectionAllowedThisIo [out]

A value of <b>TRUE</b> if this I/O can be redirected to the target device stack by changing the filter instance referenced.


### -param RedirectionAllowedAllIo [out, optional]

This optional parameter has a value of <b>TRUE</b> if all I/O to the device stack to which the I/O operation is issued can be redirected to the target device by changing the filter instance referenced,  otherwise <b>FALSE</b>.


## -returns



An NTSTATUS value of STATUS_SUCCESS for success or STATUS_NOT_SUPPORTED if the redirection is not supported.




## -remarks



An I/O operation is associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a> structure. That structure contains a reference to a <b>PFLT_IO_PARAMETER_BLOCK</b> object, which contains a reference to the FLT_INSTANCE of the minifilter associated with the I/O operation.

If <i>RedirectionAllowed</i> is <b>TRUE</b>, the minifilter can redirect I/O by changing that instance to a new target instance.

If <i>RedirectionAllowed</i> is <b>FALSE</b>, the minifilter needs to allocate a new callback data object to issue I/O on the target stack or call <a href="https://msdn.microsoft.com/library/windows/hardware/ff625873">FltAdjustDeviceStackSizeForIoRedirection</a> to increase the size of the source device stack.

<div class="alert"><b>Note</b>  Minifilters should not modify the reference to the FLT_INSTANCE before verifying that redirection can be done this way. Use <b>FltIsIoRedirectionAllowedForOperation</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff625874">FltIsIoRedirectionAllowed</a>. </div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff625873">FltAdjustDeviceStackSizeForIoRedirection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff625874">FltIsIoRedirectionAllowed</a>
 

 

