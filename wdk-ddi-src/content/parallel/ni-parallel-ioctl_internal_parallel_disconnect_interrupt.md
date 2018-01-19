---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT
title: IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT
author: windows-driver-content
description: The IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT request disconnects an interrupt service routine (and an optional deferred port check service routine) that was connected by using an IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request.
old-location: parports\ioctl_internal_parallel_disconnect_interrupt.htm
old-project: parports
ms.assetid: 9ca488b1-30d3-44dc-acb3-87d97e439393
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RegisterOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT
req.alt-loc: parallel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *LPRILGBATOKEN, RILGBATOKEN
---

# IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT IOCTL



## -description
The <b>IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</b> request disconnects an interrupt service routine (and an optional deferred port check service routine) that was connected by using an <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request. Only kernel-mode drivers can connect and disconnect an interrupt routine.



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a> structure that the client allocates for the input of interrupt service information.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a PARALLEL_INTERRUPT_SERVICE_ROUTINE structure. 


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:



The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_INTERRUPT_SERVICE_ROUTINE structure.

The specified interrupt service routine is not connected.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>
</dt>
<dt>
<a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a>
</dt>
<dt>
<a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

