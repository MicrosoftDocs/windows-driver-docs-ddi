---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_DIRECT_EX
title: "_SCSI_PASS_THROUGH_DIRECT_EX" (ntddscsi.h)
description: The SCSI_PASS_THROUGH_DIRECT_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct_ex.htm
tech.root: storage
ms.assetid: FE699F78-99AC-46E0-9C51-6F69A5C4932C
ms.date: 03/29/2018
ms.keywords: "*PSCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX structure pointer [Storage Devices], SCSI_PASS_THROUGH_DIRECT_EX, SCSI_PASS_THROUGH_DIRECT_EX structure [Storage Devices], _SCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/PSCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/SCSI_PASS_THROUGH_DIRECT_EX, storage.scsi_pass_through_direct_ex"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddscsi.h
api_name:
-	SCSI_PASS_THROUGH_DIRECT_EX
product:
- Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_DIRECT_EX, *PSCSI_PASS_THROUGH_DIRECT_EX
---

# _SCSI_PASS_THROUGH_DIRECT_EX structure

## -description

The **SCSI_PASS_THROUGH_DIRECT_EX** structure is used in conjunction with an [IOCTL_SCSI_PASS_THROUGH_DIRECT_EX](ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md) request to instruct the port driver to send an embedded SCSI command to the target device. **SCSI_PASS_THROUGH_DIRECT_EX** can contain a bi-directional data transfers and a variable length command data block.
  
> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -struct-fields

### -field Version

The version of this structure. Set to 0.

### -field Length

The size of the this structure. Set to **sizeof**(SCSI_PASS_THROUGH_DIRECT_EX).

### -field CdbLength

Indicates the size in bytes of the SCSI command descriptor block in **Cdb**.

### -field StorAddressLength

The length of the storage device address structure at the offset of **StorAddressOffset** after this structure. This is set to **sizeof**(STOR_ADDR_BTL8).

### -field ScsiStatus

Reports the SCSI status that was returned by the HBA or the target device.

### -field SenseInfoLength

Indicates the size in bytes of the request-sense buffer. This member is optional and can be set to 0.

### -field DataDirection

This field must have one of these values:

|Data Transfer Type|Meaning|
|----|----|
|SCSI_IOCTL_DATA_IN|Read data from the device.|
|SCSI_IOCTL_DATA_OUT|Write data to the device.|
|SCSI_IOCTL_DATA_UNSPECIFIED|No data is transferred.|
|SCSI_IOCTL_DATA_BIDIRECTIONAL|Data is valid for both input and output.|

### -field Reserved

Reserved. Set to 0.

### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.

### -field StorAddressOffset

The location of the target device's [STOR_ADDR_BTL8](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsi/ns-scsi-_stor_addr_btl8) address structure, in bytes, from the beginning of this structure.

### -field SenseInfoOffset

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.

### -field DataOutTransferLength

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in **DataOutTransferLength** must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.

### -field DataInTransferLength

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in **DataInTransferLength** must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.

### -field DataOutBuffer

A pointer to a output data buffer.

### -field DataInBuffer

A pointer to a input data buffer.

### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device.

## -remarks

The **SCSI_PASS_THROUGH_DIRECT_EX** structure is used with [IOCTL_SCSI_PASS_THROUGH_DIRECT_EX](ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md). With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see **IOCTL_SCSI_PASS_THROUGH_EX** and [SCSI_PASS_THROUGH_EX](ns-ntddscsi-_scsi_pass_through_ex.md).

> [!NOTE]
> Drivers executing on a 64 bit version of Windows must use the **SCSI_PASS_THROUGH_DIRECT32_EX** structure as the request data type  when handling an [IOCTL_SCSI_PASS_THROUGH_DIRECT_EX](ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md) request from a 32 bit process.

## -see-also

[IOCTL_SCSI_PASS_THROUGH_DIRECT_EX](ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md)

[IOCTL_SCSI_PASS_THROUGH_DIRECT_EX](ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md)

[SCSI_PASS_THROUGH_DIRECT](ns-ntddscsi-_scsi_pass_through_direct.md)

[STOR_ADDR_BTL8](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsi/ns-scsi-_stor_addr_btl8)
