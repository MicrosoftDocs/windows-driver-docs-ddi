---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_NVCACHE
title: IOCTL_SCSI_MINIPORT_NVCACHE (ntddscsi.h)
description: The NV Cache Management operations that are defined here can be invoked by user-mode application code running with administrator privileges, using DeviceIoControl and the IOCTL_SCSI_MINIPORT control code.
old-location: storage\ioctl_scsi_miniport_nvcache.htm
tech.root: storage
ms.assetid: 6331e850-34a7-4d03-a87b-527f3e38f735
ms.date: 03/29/2018
keywords: ["IOCTL_SCSI_MINIPORT_NVCACHE IOCTL"]
ms.keywords: IOCTL_SCSI_MINIPORT_NVCACHE, IOCTL_SCSI_MINIPORT_NVCACHE control, IOCTL_SCSI_MINIPORT_NVCACHE control code [Storage Devices], k307_0a3946a8-c611-4499-b62c-25f920eeec1e.xml, ntddscsi/IOCTL_SCSI_MINIPORT_NVCACHE, storage.ioctl_scsi_miniport_nvcache
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_SCSI_MINIPORT_NVCACHE
 - ntddscsi/IOCTL_SCSI_MINIPORT_NVCACHE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddscsi.h
api_name:
 - IOCTL_SCSI_MINIPORT_NVCACHE
---

# IOCTL_SCSI_MINIPORT_NVCACHE IOCTL

## -description

The NV Cache Management operations that are defined here can be invoked by user-mode application code running with administrator privileges, using DeviceIoControl and the [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md) control code. Or, the caller can be kernel-mode driver code using [**IoBuildDeviceIoControlRequest**](../wdm/nf-wdm-iobuilddeviceiocontrolrequest.md) and the IOCTL_SCSI_MINIPORT control code.

The NV Cache Management function request is specified in a field in the [**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md) structure. The input to [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md) is a user-defined data structure that contains an [**SRB_IO_CONTROL**](./ns-ntddscsi-_srb_io_control.md) structure followed by an **NVCACHE_REQUEST_BLOCK** structure. Additional function-specific data might optionally follow the **NVCACHE_REQUEST_BLOCK** structure.

The interface that is used for the NV Cache Management functionality consists of two layers. The first layer is the interface between a caller and the port driver, which is defined by [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md). The second layer is the interface between the caller and the device, which is defined by the ATA8-ACS specification and IOCTL_SCSI_MINIPORT_NVCACHE. The API for user-mode application code is the DeviceIoControl interface. The API for kernel-mode driver code is the [**IoBuildDeviceIoControlRequest**](../wdm/nf-wdm-iobuilddeviceiocontrolrequest.md) interface, which uses **IOCTL_SCSI_MINIPORT**.

## -ioctlparameters

### -input-buffer

The buffer at **Irp->AssociatedIrp.SystemBuffer** contains an [**SRB_IO_CONTROL**](./ns-ntddscsi-_srb_io_control.md) structure with the Signature field set to "HYBRDISK", and the ControlCode field set to IOCTL_SCSI_MINIPORT_NVCACHE. The [**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md) structure immediately follows the **SRB_IO_CONTROL** structure. Any optional function-specific data buffer immediately follows the **NVCACHE_REQUEST_BLOCK** structure.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of all the input data: [**SRB_IO_CONTROL**](./ns-ntddscsi-_srb_io_control.md), [**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md), and function-specific data buffer combined. The presence or absence of a data buffer is indicated by the **NVCACHE_REQUEST_BLOCK****DataBufSize** field.

### -output-buffer

Updated [**SRB_IO_CONTROL**](./ns-ntddscsi-_srb_io_control.md)SRB_IO_CONTROL**]() and [**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md) structures, as well as the optional function-specific data buffer, are returned to the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

The length of the buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Information** field contains the number of bytes returned in the output buffer. The **Status** field indicates the results of the operation.

## -see-also

[**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md)

[**IoBuildDeviceIoControlRequest**](../wdm/nf-wdm-iobuilddeviceiocontrolrequest.md)

[**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md)

[**SRB_IO_CONTROL**](./ns-ntddscsi-_srb_io_control.md)