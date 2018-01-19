---
UID: NI:ntddscsi.IOCTL_SCSI_GET_CAPABILITIES
title: IOCTL_SCSI_GET_CAPABILITIES
author: windows-driver-content
description: Returns the capabilities and limitations of the underlying SCSI HBA.
old-location: storage\ioctl_scsi_get_capabilities.htm
old-project: storage
ms.assetid: 1917e0f0-47a3-4f95-97d6-c60d3f511a91
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
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
req.alt-api: IOCTL_SCSI_GET_CAPABILITIES
req.alt-loc: Ntddscsi.h
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
req.typenames: *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_GET_CAPABILITIES IOCTL



## -description

Returns the capabilities and limitations of the underlying SCSI HBA. The most important information is returned in the <b>MaximumTransferLength</b> and <b>AlignmentMask </b>members. Class drivers and users of <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a> and <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> are required to honor these limitations.

Only legacy drivers can issue this request. The request fails if it is sent to a PDO created by the port driver. 

To get SCSI capabilities data, a Plug and Play driver must issue an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request for <a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a> data to the PDO for each device to which the driver has been added (that is, each device for which the driver has received an <i>AddDevice </i>call). A legacy driver should forward this request to the port driver. This request fails if it is sent to the FDO for an adapter.



Returns the capabilities and limitations of the underlying SCSI HBA. The most important information is returned in the <b>MaximumTransferLength</b> and <b>AlignmentMask </b>members. Class drivers and users of <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a> and <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> are required to honor these limitations.

Only legacy drivers can issue this request. The request fails if it is sent to a PDO created by the port driver. 

To get SCSI capabilities data, a Plug and Play driver must issue an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request for <a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a> data to the PDO for each device to which the driver has been added (that is, each device for which the driver has received an <i>AddDevice </i>call). A legacy driver should forward this request to the port driver. This request fails if it is sent to the FDO for an adapter.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
Updated <a href="..\ntddscsi\ns-ntddscsi-_io_scsi_capabilities.md">IO_SCSI_CAPABILITIES</a> information is returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(IO_SCSI_CAPABILITIES).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_io_scsi_capabilities.md">IO_SCSI_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_GET_CAPABILITIES control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

