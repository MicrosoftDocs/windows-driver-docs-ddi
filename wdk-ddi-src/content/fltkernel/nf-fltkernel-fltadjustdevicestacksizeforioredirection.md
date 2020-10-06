---
UID: NF:fltkernel.FltAdjustDeviceStackSizeForIoRedirection
title: FltAdjustDeviceStackSizeForIoRedirection function (fltkernel.h)
description: The FltAdjustDeviceStackSizeForIoRedirection routine increases the size of the source device stack to allow a minifilter to redirect I/O from a specified source instance to a specified target instance when the target stack is deeper than the source stack.
old-location: ifsk\fltadjustdevicestacksizeforioredirection.htm
tech.root: ifsk
ms.assetid: 48ca0f39-e870-4f9b-92d5-1226972bf2d5
ms.date: 04/16/2018
keywords: ["FltAdjustDeviceStackSizeForIoRedirection function"]
ms.keywords: FltAdjustDeviceStackSizeForIoRedirection, FltAdjustDeviceStackSizeForIoRedirection routine [Installable File System Drivers], fltkernel/FltAdjustDeviceStackSizeForIoRedirection, ifsk.fltadjustdevicestacksizeforioredirection
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
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAdjustDeviceStackSizeForIoRedirection
 - fltkernel/FltAdjustDeviceStackSizeForIoRedirection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAdjustDeviceStackSizeForIoRedirection
---

# FltAdjustDeviceStackSizeForIoRedirection function


## -description

The <b>FltAdjustDeviceStackSizeForIoRedirection</b> routine increases the size of the source device stack to allow a minifilter to redirect I/O from a specified source instance to a specified target instance when the target stack is deeper than the source stack.

## -parameters

### -param SourceInstance 

[in]
The filter instance on the source device stack.

### -param TargetInstance 

[in]
The filter instance on the target device stack.

### -param SourceDeviceStackSizeModified 

[out, optional]
This optional parameter has a value of <b>TRUE</b> if the <b>FltAdjustDeviceStackSizeForIoRedirection</b> routine modified the size of the source device stack, <b>FALSE</b> otherwise.

## -returns

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>
</td>
<td width="60%">
Success.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NOT_SUPPORTED</dt>
</dl>
</td>
<td width="60%">
The redirection is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The source device stack would be too large after calling this routine.

</td>
</tr>
</table>

## -remarks

Using <b>FltAdjustDeviceStackSizeForIoRedirection</b> does not guarantee that every IRP that the minifilter encounters will be sufficient in size to be redirected to the target stack. IRPs that were allocated and issued before the call to <b>FltAdjustDeviceStackSizeForIoRedirection</b> would still have been allocated based on the old stack size. 

A minifilter can adjust the stack size during instance setup if the filter knows which stack the I/O will be redirected to. 

The filter can issue its own create operation down the new stack using <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a>. Before completing the create operation, the filter can adjust the stack size to account for the target stack. Doing that adjustment ensures that the stack size will be adjusted before the create action is completed. All IRPs allocated for that file object will have a large enough stack to support redirection.

During instance-setup or during post-create callback for a redirected file object, use <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisioredirectionallowed">FltIsIoRedirectionAllowed</a> to determine if redirection is possible without modifying the source stack. If necessary, use <b>FltAdjustDeviceStackSizeForIoRedirection</b> to adjust the source stack.

In the pre-operation callback for every operation that needs redirection, use <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisioredirectionallowedforoperation">FltIsIoRedirectionAllowedForOperation</a> to determine if redirection is possible without modifying the source stack. If necessary, use <b>FltAdjustDeviceStackSizeForIoRedirection</b> to adjust the source stack.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisioredirectionallowed">FltIsIoRedirectionAllowed</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisioredirectionallowedforoperation">FltIsIoRedirectionAllowedForOperation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>