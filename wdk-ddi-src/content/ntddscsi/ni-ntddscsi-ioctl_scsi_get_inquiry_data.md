---
UID: NI:ntddscsi.IOCTL_SCSI_GET_INQUIRY_DATA
title: IOCTL_SCSI_GET_INQUIRY_DATA (ntddscsi.h)
description: Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA).
old-location: storage\ioctl_scsi_get_inquiry_data.htm
tech.root: storage
ms.assetid: a429061b-ede6-48b1-9fc6-e85e4a7c0dfe
ms.date: 03/29/2018
keywords: ["IOCTL_SCSI_GET_INQUIRY_DATA IOCTL"]
ms.keywords: IOCTL_SCSI_GET_INQUIRY_DATA, IOCTL_SCSI_GET_INQUIRY_DATA control, IOCTL_SCSI_GET_INQUIRY_DATA control code [Storage Devices], k307_7565e2a4-7599-4c7e-8da1-24349978627e.xml, ntddscsi/IOCTL_SCSI_GET_INQUIRY_DATA, storage.ioctl_scsi_get_inquiry_data
f1_keywords:
 - "ntddscsi/IOCTL_SCSI_GET_INQUIRY_DATA"
 - "IOCTL_SCSI_GET_INQUIRY_DATA"
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
- IOCTL_SCSI_GET_INQUIRY_DATA
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_GET_INQUIRY_DATA IOCTL


## -description



Returns the SCSI inquiry data for all devices on a given SCSI host bus adapter (HBA). If the IOCTL is employed in user space, the program must have opened a handle to the HBA, which can be enumerated by various means, such as SetupDixxx calls. You can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> to find information about a specific device on the HBA. To determine the size of the output buffer that is required, the caller should send this IOCTL request in a loop. Every time that the storage stack rejects the IOCTL with an error message that indicates that the buffer was too small, the caller should double the buffer size.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver-overview">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the returned inquiry data. For a description of the layout of the inquiry data in the output buffer, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_adapter_bus_info">SCSI_ADAPTER_BUS_INFO</a>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer, which must be >= (<b>sizeof</b>(SCSI_ADAPTER_BUS_INFO) + (<i>NumberOfBuses</i>) * <b>sizeof</b>(SCSI_BUS_DATA)) + (<i>InquiryDataSize</i> * <i>NumberOfLUs</i>), where the <i>InquiryDataSize</i> is (<b>sizeof</b>(SCSI_INQUIRY_DATA) - 1 + INQUIRYDATABUFFERSIZE) rounded up to an alignment boundary.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_miniport">IOCTL_SCSI_MINIPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through">IOCTL_SCSI_PASS_THROUGH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_rescan_bus">IOCTL_SCSI_RESCAN_BUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_adapter_bus_info">SCSI_ADAPTER_BUS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_inquiry_data">SCSI_INQUIRY_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>
 

 

