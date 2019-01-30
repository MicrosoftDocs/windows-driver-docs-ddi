---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_DIRECT
title: "_SCSI_PASS_THROUGH_DIRECT" (ntddscsi.h)
description: The SCSI_PASS_THROUGH_DIRECT structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct.htm
tech.root: storage
ms.assetid: 306babe7-393f-4b4a-9d8a-4c973cb3eaa2
ms.date: 03/29/2018
ms.keywords: "*PSCSI_PASS_THROUGH_DIRECT, PSCSI_PASS_THROUGH_DIRECT, PSCSI_PASS_THROUGH_DIRECT structure pointer [Storage Devices], SCSI_PASS_THROUGH_DIRECT, SCSI_PASS_THROUGH_DIRECT structure [Storage Devices], _SCSI_PASS_THROUGH_DIRECT, ntddscsi/PSCSI_PASS_THROUGH_DIRECT, ntddscsi/SCSI_PASS_THROUGH_DIRECT, storage.scsi_pass_through_direct, structs-scsibus_64c46eef-e5bc-4e81-a479-2bdbd93605e7.xml"
ms.topic: struct
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
-	ntddscsi.h
api_name:
-	SCSI_PASS_THROUGH_DIRECT
product:
- Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_DIRECT, *PSCSI_PASS_THROUGH_DIRECT
---

# _SCSI_PASS_THROUGH_DIRECT structure

## -description

The **SCSI_PASS_THROUGH_DIRECT** structure is used in conjunction with an [IOCTL_SCSI_PASS_THROUGH_DIRECT](ni-ntddscsi-ioctl_scsi_pass_through_direct.md) request to instruct the port driver to send an embedded SCSI command to the target device.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](https://docs.microsoft.com/windows-hardware/drivers/storage/storage-miniport-drivers) driver models.

## -struct-fields

### -field Length

Contains the value of **sizeof**(SCSI_PASS_THROUGH_DIRECT).  

### -field ScsiStatus

Reports the SCSI status that was returned by the HBA or the target device.

### -field PathId

Indicates the SCSI port or bus for the request.

### -field TargetId

Indicates the target controller or device on the bus.  

### -field Lun

Indicates the logical unit number of the device.

### -field CdbLength

Indicates the size in bytes of the SCSI command descriptor block.

### -field SenseInfoLength

Indicates the size in bytes of the request-sense buffer.

### -field DataIn

Indicates whether the SCSI command will read or write data. This field must have one of three values:

|Data Transfer Type|Meaning|
|----|----|
|SCSI_IOCTL_DATA_IN|Read data from the device.|
|SCSI_IOCTL_DATA_OUT|Write data to the device.|
|SCSI_IOCTL_DATA_UNSPECIFIED|No data transferred.|

### -field DataTransferLength

Indicates the size in bytes of the data buffer. Many devices transfer chunks of data of predefined length. The value in **DataTransferLength** must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.

### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out.

### -field DataBuffer

Pointer to the data buffer.

### -field SenseInfoOffset

Contains an offset from the beginning of this structure to the request-sense buffer.

### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device.

## -remarks

The SCSI_PASS_THROUGH_DIRECT structure is used with [IOCTL_SCSI_PASS_THROUGH_DIRECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct). With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see [IOCTL_SCSI_PASS_THROUGH](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through) and [SCSI_PASS_THROUGH](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through).

The members of SCSI_PASS_THROUGH_DIRECT correspond roughly to the members of a [SCSI_REQUEST_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block) structure. The values of the **DataIn** member correspond to the SCSI_IOCTL_DATA_IN, SCSI_IOCTL_DATA_OUT, and SCSI_IOCTL_DATA_UNSPECIFIED flags assigned to **SrbFlags** member of SCSI_REQUEST_BLOCK.

## -see-also

[IOCTL_SCSI_PASS_THROUGH](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through)

[IOCTL_SCSI_PASS_THROUGH_DIRECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_pass_through_direct)

[SCSI_PASS_THROUGH](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_pass_through)

[SCSI_REQUEST_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block)
