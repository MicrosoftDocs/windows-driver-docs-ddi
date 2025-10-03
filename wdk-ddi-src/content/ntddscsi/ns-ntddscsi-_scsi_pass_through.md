---
UID: NS:ntddscsi._SCSI_PASS_THROUGH
title: SCSI_PASS_THROUGH (ntddscsi.h)
description: The SCSI_PASS_THROUGH structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH request to instruct the port driver to send an embedded SCSI command to the target device.
tech.root: storage
ms.date: 09/22/2025
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
req.typenames: SCSI_PASS_THROUGH, *PSCSI_PASS_THROUGH
f1_keywords:
 - _SCSI_PASS_THROUGH
 - ntddscsi/_SCSI_PASS_THROUGH
 - PSCSI_PASS_THROUGH
 - ntddscsi/PSCSI_PASS_THROUGH
 - SCSI_PASS_THROUGH
 - ntddscsi/SCSI_PASS_THROUGH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _SCSI_PASS_THROUGH
 - PSCSI_PASS_THROUGH
 - SCSI_PASS_THROUGH
---

# SCSI_PASS_THROUGH structure

## -description

The SCSI_PASS_THROUGH structure is used in conjunction with an [IOCTL_SCSI_PASS_THROUGH](ni-ntddscsi-ioctl_scsi_pass_through.md) request to instruct the port driver to send an embedded SCSI command to the target device.

> **Note**  
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver-overview) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

The SCSI_PASS_THROUGH structure is used in conjunction with an [IOCTL_SCSI_PASS_THROUGH](ni-ntddscsi-ioctl_scsi_pass_through.md) request to instruct the port driver to send an embedded SCSI command to the target device.

## -struct-fields

### -field Length

Contains the value of **sizeof**(SCSI_PASS_THROUGH).

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

| Value | Meaning |
| ----- | ------- |
| SCSI_IOCTL_DATA_OUT (0) | Write data to the device |
| SCSI_IOCTL_DATA_IN (1) | Read data from the device |
| SCSI_IOCTL_DATA_UNSPECIFIED (2) | No data transfer or transfer direction is unknown |

### -field DataTransferLength

Indicates the size in bytes of the data buffer. Many devices transfer chunks of data of predefined length. The value in **DataTransferLength** must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.

### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the port driver considers it timed out. Do not set this value to 0. Default values often range from:

* Typical operations: 30 to 60 seconds
* Short operations: 10 to 30 seconds
* Medium operations: 30 to 120 seconds
* Long operations (like format, extended self-test): 300 to 3600 seconds or more

### -field DataBufferOffset

Contains an offset from the beginning of this structure to the data buffer. The offset must respect the data alignment requirements of the device.

### -field SenseInfoOffset

Offset from the beginning of this structure to the request-sense buffer.

### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device.

## -remarks

The SCSI_PASS_THROUGH structure is used with [IOCTL_SCSI_PASS_THROUGH](ni-ntddscsi-ioctl_scsi_pass_through.md), which is a buffered device control request. To bypass buffering in system memory, callers should use [IOCTL_SCSI_PASS_THROUGH_DIRECT](ni-ntddscsi-ioctl_scsi_pass_through_direct.md). When handling an IOCTL_SCSI_PASS_THROUGH_DIRECT request, the system locks down the buffer in user memory and the device accesses this memory directly.

The members of SCSI_PASS_THROUGH correspond roughly to the members of a [SCSI_REQUEST_BLOCK](../srb/ns-srb-_scsi_request_block.md) structure. The values of the **DataIn** member correspond to the SCSI_IOCTL_DATA_IN, SCSI_IOCTL_DATA_OUT, and SCSI_IOCTL_DATA_UNSPECIFIED flags assigned to **SrbFlags** member of SCSI_REQUEST_BLOCK.

## -see-also

[IOCTL_SCSI_PASS_THROUGH](ni-ntddscsi-ioctl_scsi_pass_through.md)

[IOCTL_SCSI_PASS_THROUGH_DIRECT](ni-ntddscsi-ioctl_scsi_pass_through_direct.md)

[SCSI_PASS_THROUGH_DIRECT](ns-ntddscsi-_scsi_pass_through_direct.md)

[SCSI_REQUEST_BLOCK](../srb/ns-srb-_scsi_request_block.md)
