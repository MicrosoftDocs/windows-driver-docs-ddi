---
UID: NI:ntddscsi.IOCTL_SCSI_GET_ADDRESS
title: IOCTL_SCSI_GET_ADDRESS (ntddscsi.h)
description: Returns the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target.
old-location: storage\ioctl_scsi_get_address.htm
tech.root: storage
ms.assetid: 56e2a62c-ecf1-45c8-ba65-fb53b1897ddb
ms.date: 11/07/2019
keywords: ["IOCTL_SCSI_GET_ADDRESS IOCTL"]
ms.keywords: IOCTL_SCSI_GET_ADDRESS, IOCTL_SCSI_GET_ADDRESS control, IOCTL_SCSI_GET_ADDRESS control code [Storage Devices], k307_0d205fdd-0951-42ef-bd5c-09727bee65f4.xml, ntddscsi/IOCTL_SCSI_GET_ADDRESS, storage.ioctl_scsi_get_address
f1_keywords:
 - "ntddscsi/IOCTL_SCSI_GET_ADDRESS"
 - "IOCTL_SCSI_GET_ADDRESS"
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
- IOCTL_SCSI_GET_ADDRESS
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_GET_ADDRESS IOCTL

## -description

Returns the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target. A legacy class driver can issue this request to the port driver to obtain the address of its device. On Windows 10 version 1809 and later versions, a legacy class driver can issue this request to obtain the address of its adapter.

This request is not relevant to storage class drivers that support Plug and Play because the port driver supplies the address information on behalf of the class driver.

This request must be directed to a class driver or to a PDO created by the port driver.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver-overview) and [Storport miniport](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

Updated [SCSI_ADDRESS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_address) information is returned to the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location indicates the size, in bytes, of the buffer, which must be >= **sizeof**([SCSI_ADDRESS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_address)).

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Information** field contains the number of bytes returned in the output buffer. The **Status** field indicates the results of the operation.

## -see-also

[SCSI_ADDRESS](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_scsi_address)
