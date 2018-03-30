---
UID: NI:ntddscsi.IOCTL_SCSI_GET_CAPABILITIES
title: IOCTL_SCSI_GET_CAPABILITIES
author: windows-driver-content
description: Returns the capabilities and limitations of the underlying SCSI HBA.
old-location: storage\ioctl_scsi_get_capabilities.htm
old-project: storage
ms.assetid: 1917e0f0-47a3-4f95-97d6-c60d3f511a91
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_SCSI_GET_CAPABILITIES, IOCTL_SCSI_GET_CAPABILITIES control code [Storage Devices], k307_99c3b622-6b7f-4550-9740-22b46d141966.xml, ntddscsi/IOCTL_SCSI_GET_CAPABILITIES, storage.ioctl_scsi_get_capabilities
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
-	IOCTL_SCSI_GET_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_GET_CAPABILITIES IOCTL


## -description



Returns the capabilities and limitations of the underlying SCSI HBA. The most important information is returned in the <b>MaximumTransferLength</b> and <b>AlignmentMask </b>members. Class drivers and users of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> are required to honor these limitations.

Only legacy drivers can issue this request. The request fails if it is sent to a PDO created by the port driver. 

To get SCSI capabilities data, a Plug and Play driver must issue an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request for <a href="https://msdn.microsoft.com/library/windows/hardware/ff566346">STORAGE_ADAPTER_DESCRIPTOR</a> data to the PDO for each device to which the driver has been added (that is, each device for which the driver has received an <i>AddDevice </i>call). A legacy driver should forward this request to the port driver. This request fails if it is sent to the FDO for an adapter.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

Updated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561471">IO_SCSI_CAPABILITIES</a> information is returned to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(IO_SCSI_CAPABILITIES).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561471">IO_SCSI_CAPABILITIES</a>
 

 

