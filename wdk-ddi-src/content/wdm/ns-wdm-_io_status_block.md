---
UID: NS:wdm._IO_STATUS_BLOCK
title: _IO_STATUS_BLOCK (wdm.h)
description: A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling IoCompleteRequest for the IRP.
old-location: kernel\io_status_block.htm
tech.root: kernel
ms.assetid: 1ce2b1d0-a8b2-4a05-8895-e13802690a7b
ms.date: 04/30/2018
keywords: ["_IO_STATUS_BLOCK structure"]
ms.keywords: "*PIO_STATUS_BLOCK, IO_STATUS_BLOCK, IO_STATUS_BLOCK structure [Kernel-Mode Driver Architecture], PIO_STATUS_BLOCK, PIO_STATUS_BLOCK structure pointer [Kernel-Mode Driver Architecture], _IO_STATUS_BLOCK, kernel.io_status_block, kstruct_b_f0869bcd-fcf0-427a-9bda-fc925c0bf0f8.xml, wdm/IO_STATUS_BLOCK, wdm/PIO_STATUS_BLOCK"
f1_keywords:
 - "wdm/IO_STATUS_BLOCK"
 - "IO_STATUS_BLOCK"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IO_STATUS_BLOCK
product:
- Windows
targetos: Windows
req.typenames: IO_STATUS_BLOCK, *PIO_STATUS_BLOCK
---

# _IO_STATUS_BLOCK structure


## -description


A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a> for the IRP.


## -struct-fields




### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.Status

This is the completion status, either STATUS_SUCCESS if the requested operation was completed successfully or an informational, warning, or error STATUS_<i>XXX</i> value. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS values</a>.


### -field DUMMYUNIONNAME.Pointer

Reserved. For internal use only.


### -field Information

This is set to a request-dependent value. For example, on successful completion of a transfer request, this is set to the number of bytes transferred. If a transfer request is completed with another STATUS_<i>XXX</i>, this member is set to zero. 


## -remarks



Unless a driver's dispatch routine completes an IRP with an error status value, the lowest-level driver in the chain frequently sets the IRP's I/O status block to the values that will be returned to the original requester of the I/O operation.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routines of higher-level drivers usually check the I/O status block in IRPs completed by lower drivers. By design, the I/O status block in an IRP is the only information passed back from the underlying device driver to all higher-level drivers' <i>IoCompletion</i> routines.

The operating system implements <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">support routines</a> that write <b>IO_STATUS_BLOCK</b> values to caller-supplied output buffers. For example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a> or <a href="https://go.microsoft.com/fwlink/p/?linkid=155044">NtOpenFile</a>. These routines return status codes that might not match the status codes in the <b>IO_STATUS_BLOCK</b> structures. If one of these routines returns STATUS_PENDING, the caller should wait for the I/O operation to complete, and then check the status code in the <b>IO_STATUS_BLOCK</b> structure to determine the final status of the operation. If the routine returns a status code other than STATUS_PENDING, the caller should rely on this status code instead of the status code in the <b>IO_STATUS_BLOCK</b> structure.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-status-blocks">I/O Status Blocks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a>
 

 

