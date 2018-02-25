---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT
title: IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT
author: windows-driver-content
description: The IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request connects an optional interrupt service routine and an optional deferred port check routine to a parallel port.
old-location: parports\ioctl_internal_parallel_connect_interrupt.htm
old-project: parports
ms.assetid: 8cf5f2fc-e298-4f5b-bca4-3034e8a4a061
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT, IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT control code [Parallel Ports], cisspd_b43103ce-7b3e-413b-914c-fbaf1d7789ee.xml, parallel/IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT, parports.ioctl_internal_parallel_connect_interrupt
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
-	IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</b> request connects an optional interrupt service routine and an optional <i>deferred port check</i> routine to a parallel port. Only kernel-mode drivers can use this request.

The connect interrupt request returns information that the driver can use in the context of a driver-specific ISR. The information includes a pointer to the interrupt object and pointers to callback routines that allocate and free the parallel port at IRQL = DIRQL.
<div class="alert"><b>Note</b>    Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the connect interrupt request is disabled. For more information, see <a href="https://msdn.microsoft.com/62d3a388-6de6-4019-ab95-56b5e96d0891">Connecting an Interrupt Service Routine to a ParallelPort</a>.</div><div> </div>

## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a> structure that the client allocates to input interrupt service information. The system-supplied function driver for parallel ports uses the same memory buffer, but casts it to a different data type to output information.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a PARALLEL_INTERRUPT_SERVICE_ROUTINE structure.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a PARALLEL_INTERRUPT_INFORMATION structure that the parallel port function driver uses to output parallel interrupt information. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a> structure. Otherwise, the <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

At least one of the following is true: 

The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_INTERRUPT_SERVICE_ROUTINE structure. 

The value of the <b>Parameters.DeviceIoControl.OuputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_INTERRUPT_INFORMATION structure. 


## -see-also

<a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md">IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</a>



<a href="..\parallel\ns-parallel-_parallel_interrupt_information.md">PARALLEL_INTERRUPT_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

