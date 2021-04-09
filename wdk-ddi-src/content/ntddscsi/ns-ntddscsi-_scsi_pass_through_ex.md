---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_EX
title: SCSI_PASS_THROUGH_EX (ntddscsi.h)
description: The SCSI_PASS_THROUGH_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_ex.htm
tech.root: storage
ms.date: 04/09/2021
keywords: ["SCSI_PASS_THROUGH_EX structure"]
ms.keywords: "*PSCSI_PASS_THROUGH_EX, PSCSI_PASS_THROUGH_EX, PSCSI_PASS_THROUGH_EX structure pointer [Storage Devices], SCSI_PASS_THROUGH_EX, SCSI_PASS_THROUGH_EX structure [Storage Devices], _SCSI_PASS_THROUGH_EX, ntddscsi/PSCSI_PASS_THROUGH_EX, ntddscsi/SCSI_PASS_THROUGH_EX, storage.scsi_pass_through_ex"
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: SCSI_PASS_THROUGH_EX, *PSCSI_PASS_THROUGH_EX
f1_keywords:
 - _SCSI_PASS_THROUGH_EX
 - ntddscsi/_SCSI_PASS_THROUGH_EX
 - PSCSI_PASS_THROUGH_EX
 - ntddscsi/PSCSI_PASS_THROUGH_EX
 - SCSI_PASS_THROUGH_EX
 - ntddscsi/SCSI_PASS_THROUGH_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _SCSI_PASS_THROUGH_EX
 - PSCSI_PASS_THROUGH_EX
 - SCSI_PASS_THROUGH_EX
---

# SCSI_PASS_THROUGH_EX structure

## -description

The **SCSI_PASS_THROUGH_EX** structure is used in conjunction with an **IOCTL_SCSI_PASS_THROUGH_EX** request to instruct the port driver to send an embedded SCSI command to the target device. **SCSI_PASS_THROUGH_EX** can contain a bi-directional data transfers and a variable length command data block.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, use the [Storport driver](/windows-hardware/drivers/storage/storport-driver-overview) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -struct-fields

### -field Version

The version of this structure. Set to 0.

### -field Length

The size of this structure, in bytes. Set to ```sizeof(SCSI_PASS_THROUGH_EX)```.

### -field CdbLength

The size of the SCSI command descriptor block in **Cdb**, in bytes.

### -field StorAddressLength

The length, in bytes, of the storage device address structure at the offset of **StorAddressOffset** after this structure.

### -field ScsiStatus

Reports the SCSI status that was returned by the HBA or the target device.

### -field SenseInfoLength

The size in bytes of the request-sense buffer. This member is optional and can be set to 0.

### -field DataDirection

Indicates whether the SCSI command will read or write data. This field must be one of the following values:

| Value | Meaning |
| ----- | ------- |
| SCSI_IOCTL_DATA_OUT                | Write data to the device.                |
| SCSI_IOCTL_DATA_IN                 | Read data from the device.               |
| SCSI_IOCTL_DATA_UNSPECIFIED        | No data is being transferred.            |
| SCSI_IOCTL_DATA_BIDIRECTIONAL      | Data is valid for both input and output. |

### -field Reserved

Reserved. Set to 0.

### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.

### -field StorAddressOffset

The location of the target storage device address structure, in bytes, from the beginning of this structure.

### -field SenseInfoOffset

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.

### -field DataOutTransferLength

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in **DataOutTransferLength** must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.

### -field DataInTransferLength

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in **DataInTransferLength** must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.

### -field DataOutBufferOffset

Contains an offset from the beginning of this structure to the output data buffer. The offset must respect the data alignment requirements of the device.

### -field DataInBufferOffset

Contains an offset from the beginning of this structure to the input data buffer. The offset must respect the data alignment requirements of the device.

### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device.

## -remarks

The **SCSI_PASS_THROUGH_EX** structure is used with the [**IOCTL_SCSI_PASS_THROUGH_EX**](ni-ntddscsi-ioctl_scsi_pass_through_ex.md) control code, which is a buffered device control request. To bypass buffering in system memory, callers should use [**IOCTL_SCSI_PASS_THROUGH_DIRECT_EX**](ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md). When handling an **IOCTL_SCSI_PASS_THROUGH_DIRECT_EX** request, the system locks down the buffer in user memory and the device accesses this memory directly.

> [!NOTE]
> Drivers executing on a 64-bit version of Windows must use the **SCSI_PASS_THROUGH32_EX** structure as the request data type when handling an [**IOCTL_SCSI_PASS_THROUGH_EX**](ni-ntddscsi-ioctl_scsi_pass_through_ex.md) request from a 32-bit process.

## -see-also

[**IOCTL_SCSI_PASS_THROUGH**](ni-ntddscsi-ioctl_scsi_pass_through.md)

[**IOCTL_SCSI_PASS_THROUGH_EX**](ni-ntddscsi-ioctl_scsi_pass_through_ex.md)

[**SCSI_PASS_THROUGH**](ns-ntddscsi-_scsi_pass_through.md)
