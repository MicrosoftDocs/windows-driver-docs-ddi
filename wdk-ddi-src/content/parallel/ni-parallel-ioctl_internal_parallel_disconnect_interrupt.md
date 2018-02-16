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
ms.keywords: parports.ioctl_internal_parallel_disconnect_interrupt, IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT control code [Parallel Ports], IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT, parallel/IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT, cisspd_d98e5171-686e-41de-96fd-4615eaad82f3.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	parallel.h
apiname:
-	IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT
product: Windows
targetos: Windows
req.typenames: "*LPRILGBATOKEN, RILGBATOKEN"
---

# IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</b> request disconnects an interrupt service routine (and an optional deferred port check service routine) that was connected by using an <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request. Only kernel-mode drivers can connect and disconnect an interrupt routine.
<div class="alert"><b>Note</b>    Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the connect interrupt request is disabled. For more information, see <a href="https://msdn.microsoft.com/62d3a388-6de6-4019-ab95-56b5e96d0891">Connecting an Interrupt Service Routine to a ParallelPort</a>.</div><div> </div>

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

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_INTERRUPT_SERVICE_ROUTINE structure.


#### -STATUS_INVALID_PARAMETER

The specified interrupt service routine is not connected.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>



<a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a>



<a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

