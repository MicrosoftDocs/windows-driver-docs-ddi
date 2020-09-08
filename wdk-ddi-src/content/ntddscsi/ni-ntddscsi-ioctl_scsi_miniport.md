---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT
title: IOCTL_SCSI_MINIPORT (ntddscsi.h)
description: Sends a special control function to an HBA-specific miniport driver.
old-location: storage\ioctl_scsi_miniport.htm
tech.root: storage
ms.assetid: 5a9facc7-c83e-4dd4-9fb4-e3385c1b94ea
ms.date: 12/20/2019
keywords: ["IOCTL_SCSI_MINIPORT IOCTL"]
ms.keywords: IOCTL_SCSI_MINIPORT, IOCTL_SCSI_MINIPORT control, IOCTL_SCSI_MINIPORT control code [Storage Devices], k307_49b821f3-1a79-44aa-a6a1-92543177181d.xml, ntddscsi/IOCTL_SCSI_MINIPORT, storage.ioctl_scsi_miniport
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
 - IOCTL_SCSI_MINIPORT
 - ntddscsi/IOCTL_SCSI_MINIPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddscsi.h
api_name:
 - IOCTL_SCSI_MINIPORT
---

# IOCTL_SCSI_MINIPORT IOCTL


## -description

Sends a special control function to a host bus adapter-specific (HBA) miniport driver. Results vary, depending on the particular miniport driver to which this request is forwarded. If the caller specifies a nonzero **Length**, either the input or output buffer must be at least (**sizeof**(SRB_IO_CONTROL) + *DataBufferLength*)).

The prescribed way to open the HBA is use the [SetupDi*Xxx* APIs](https://docs.microsoft.com/windows-hardware/drivers/install/using-device-installation-functions#ddk-setupdi-setup-class-functions-dg) to get all the ScsiAdapter class devices that are running. Get the properties of each for their device instance name and open the HBA directly. SCSI%d (for example, \\\\.\Scsi0:) is a symbolic link and not ALL storage drivers create the link.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver-overview) and [Storport miniport](https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -ioctlparameters

### -input-buffer

The buffer at **Irp->AssociatedIrp.SystemBuffer** must contain an [SRB_IO_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control) structure.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the buffer, which must be at least **sizeof**(SRB_IO_CONTROL), with additional storage for data if the **Length** field is nonzero.

### -output-buffer

An updated [SRB_IO_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control) structure is returned to the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -output-buffer-length

The length of the [SRB_IO_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control) structure.

### -status-block

The **Information** field contains the number of bytes returned in the output buffer. The **Status** field indicates the results of the operation.

## -see-also

[SRB_IO_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control)

