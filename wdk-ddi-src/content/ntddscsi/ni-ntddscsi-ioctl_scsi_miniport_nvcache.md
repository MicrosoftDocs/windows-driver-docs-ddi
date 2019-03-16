---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_NVCACHE
title: IOCTL_SCSI_MINIPORT_NVCACHE (ntddscsi.h)
description: The NV Cache Management operations that are defined here can be invoked by user-mode application code running with administrator privileges, using DeviceIoControl and the IOCTL_SCSI_MINIPORT control code.
old-location: storage\ioctl_scsi_miniport_nvcache.htm
tech.root: storage
ms.assetid: 6331e850-34a7-4d03-a87b-527f3e38f735
ms.date: 03/29/2018
ms.keywords: IOCTL_SCSI_MINIPORT_NVCACHE, IOCTL_SCSI_MINIPORT_NVCACHE control, IOCTL_SCSI_MINIPORT_NVCACHE control code [Storage Devices], k307_0a3946a8-c611-4499-b62c-25f920eeec1e.xml, ntddscsi/IOCTL_SCSI_MINIPORT_NVCACHE, storage.ioctl_scsi_miniport_nvcache
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
- Ntddscsi.h
api_name:
- IOCTL_SCSI_MINIPORT_NVCACHE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_MINIPORT_NVCACHE IOCTL


## -description



The NV Cache Management operations that are defined here can be invoked by user-mode application code running with administrator privileges, using DeviceIoControl and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560512">IOCTL_SCSI_MINIPORT</a> control code. Or, the caller can be kernel-mode driver code using <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a> and the IOCTL_SCSI_MINIPORT control code.

The NV Cache Management function request is specified in a field in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563241">NVCACHE_REQUEST_BLOCK</a> structure. The input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560512">IOCTL_SCSI_MINIPORT</a> is a user-defined data structure that contains an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566339">SRB_IO_CONTROL</a> structure followed by an <b>NVCACHE_REQUEST_BLOCK</b> structure. Additional function-specific data might optionally follow the <b>NVCACHE_REQUEST_BLOCK</b> structure.

The interface that is used for the NV Cache Management functionality consists of two layers. The first layer is the interface between a caller and the port driver, which is defined by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560512">IOCTL_SCSI_MINIPORT</a>. The second layer is the interface between the caller and the device, which is defined by the <a href="https://go.microsoft.com/fwlink/p/?linkid=74996">ATA8-ACS specification</a> and IOCTL_SCSI_MINIPORT_NVCACHE. The API for user-mode application code is the DeviceIoControl interface. The API for kernel-mode driver code is the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a> interface, which uses <b>IOCTL_SCSI_MINIPORT</b>.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566339">SRB_IO_CONTROL</a> structure with the Signature field set to "HYBRDISK", and the ControlCode field set to IOCTL_SCSI_MINIPORT_NVCACHE. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff563241">NVCACHE_REQUEST_BLOCK</a> structure immediately follows the <b>SRB_IO_CONTROL</b> structure. Any optional function-specific data buffer immediately follows the <b>NVCACHE_REQUEST_BLOCK</b> structure. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of all the input data:  <a href="https://msdn.microsoft.com/library/windows/hardware/ff566339">SRB_IO_CONTROL</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563241">NVCACHE_REQUEST_BLOCK</a>, and function-specific data buffer combined. The presence or absence of a data buffer is indicated by the <b>NVCACHE_REQUEST_BLOCK</b><b>DataBufSize</b> field.


### -output-buffer

Updated <a href="https://msdn.microsoft.com/library/windows/hardware/ff566339">SRB_IO_CONTROL</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563241">NVCACHE_REQUEST_BLOCK</a> structures, as well as the optional function-specific data buffer, are returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

The length of the buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560512">IOCTL_SCSI_MINIPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563241">NVCACHE_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566339">SRB_IO_CONTROL</a>
 

 

