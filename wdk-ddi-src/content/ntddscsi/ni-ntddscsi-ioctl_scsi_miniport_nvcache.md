---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_NVCACHE
title: IOCTL_SCSI_MINIPORT_NVCACHE
author: windows-driver-content
description: The NV Cache Management operations that are defined here can be invoked by user-mode application code running with administrator privileges, using DeviceIoControl and the IOCTL_SCSI_MINIPORT control code.
old-location: storage\ioctl_scsi_miniport_nvcache.htm
old-project: storage
ms.assetid: 6331e850-34a7-4d03-a87b-527f3e38f735
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_SCSI_MINIPORT_NVCACHE, IOCTL_SCSI_MINIPORT_NVCACHE control code [Storage Devices], k307_0a3946a8-c611-4499-b62c-25f920eeec1e.xml, ntddscsi/IOCTL_SCSI_MINIPORT_NVCACHE, storage.ioctl_scsi_miniport_nvcache
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddscsi.h
api_name:
-	IOCTL_SCSI_MINIPORT_NVCACHE
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_MINIPORT_NVCACHE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The NV Cache Management operations that are defined here can be invoked by user-mode application code running with administrator privileges, using DeviceIoControl and the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a> control code. Or, the caller can be kernel-mode driver code using <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> and the IOCTL_SCSI_MINIPORT control code.

The NV Cache Management function request is specified in a field in the <a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a> structure. The input to <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a> is a user-defined data structure that contains an <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure followed by an <b>NVCACHE_REQUEST_BLOCK</b> structure. Additional function-specific data might optionally follow the <b>NVCACHE_REQUEST_BLOCK</b> structure.

The interface that is used for the NV Cache Management functionality consists of two layers. The first layer is the interface between a caller and the port driver, which is defined by <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>. The second layer is the interface between the caller and the device, which is defined by the <a href="http://go.microsoft.com/fwlink/p/?linkid=74996">ATA8-ACS specification</a> and IOCTL_SCSI_MINIPORT_NVCACHE. The API for user-mode application code is the DeviceIoControl interface. The API for kernel-mode driver code is the <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> interface, which uses <b>IOCTL_SCSI_MINIPORT</b>.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure with the Signature field set to "HYBRDISK", and the ControlCode field set to IOCTL_SCSI_MINIPORT_NVCACHE. The <a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a> structure immediately follows the <b>SRB_IO_CONTROL</b> structure. Any optional function-specific data buffer immediately follows the <b>NVCACHE_REQUEST_BLOCK</b> structure. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of all the input data:  <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a>, <a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a>, and function-specific data buffer combined. The presence or absence of a data buffer is indicated by the <b>NVCACHE_REQUEST_BLOCK</b><b>DataBufSize</b> field.


### -output-buffer

Updated <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> and <a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a> structures, as well as the optional function-specific data buffer, are returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

The length of the buffer.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -see-also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>



<a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a>



<a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a>



<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_MINIPORT_NVCACHE control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

