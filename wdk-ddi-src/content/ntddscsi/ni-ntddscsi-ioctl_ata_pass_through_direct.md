---
UID: NI:ntddscsi.IOCTL_ATA_PASS_THROUGH_DIRECT
title: IOCTL_ATA_PASS_THROUGH_DIRECT (ntddscsi.h)
description: Learn how IOCTL_ATA_PASS_THROUGH_DIRECT allows an application to send almost any ATA command to a target device.
old-location: storage\ioctl_ata_pass_through_direct.htm
tech.root: storage
ms.date: 10/19/2021
keywords: ["IOCTL_ATA_PASS_THROUGH_DIRECT IOCTL"]
ms.keywords: IOCTL_ATA_PASS_THROUGH_DIRECT, IOCTL_ATA_PASS_THROUGH_DIRECT control, IOCTL_ATA_PASS_THROUGH_DIRECT control code [Storage Devices], k307_8f1da276-e1bf-405e-8e01-a633b8671d5f.xml, ntddscsi/IOCTL_ATA_PASS_THROUGH_DIRECT, storage.ioctl_ata_pass_through_direct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Server 2003
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
 - IOCTL_ATA_PASS_THROUGH_DIRECT
 - ntddscsi/IOCTL_ATA_PASS_THROUGH_DIRECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddscsi.h
api_name:
 - IOCTL_ATA_PASS_THROUGH_DIRECT
---

# IOCTL_ATA_PASS_THROUGH_DIRECT IOCTL

## -description

**IOCTL_ATA_PASS_THROUGH_DIRECT** allows an application to send almost any ATA command to a target device, with the following restrictions:

* If a class driver for the target type of device exists, the application must send the request to the class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the device.

* The application *must* use this request rather than [**IOCTL_ATA_PASS_THROUGH**](ni-ntddscsi-ioctl_ata_pass_through.md) if the embedded ATA command might require the underlying miniport driver to access memory directly.

If the ATA command requests a data transfer operation, the caller must set up a cache-aligned buffer from which, or into which, the driver can transfer data directly. The caller should ensure the following:

* The data transfer length satisfies the device's I/O alignment requirement; otherwise, this IOCTL fails with STATUS_INVALID_PARAMETER.
* The data transfer length should not be greater than the device's maximum I/O transfer length; otherwise, it is expected that the device will fail the request.

The **IOCTL_ATA_PASS_THROUGH_DIRECT** request is typically used for transferring large amounts of data (more than 16 KB).

## -ioctlparameters

### -input-buffer

The buffer at **Irp->AssociatedIrp.SystemBuffer** contains an [**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md) structure that includes a set of task file input registers that indicate the sort of command to be performed. The caller must initialize all the members of this structure except for **PathId**, **TargetId**, and **Lun**, which the port driver fills in. For a data-out command, the **DataBuffer** member of **ATA_PASS_THROUGH_DIRECT** must point to a cache-aligned buffer containing the data to be written.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size in bytes of the buffer at **Irp->AssociatedIrp.SystemBuffer**. The value of **InputBufferLength** is fixed and does not depend on the amount of data transferred. It is equal to **sizeof(ATA_PASS_THROUGH_DIRECT)**. If the size of the buffer is less than **sizeof(ATA_PASS_THROUGH_DIRECT)**, the port driver fails the I/O request and returns an error.

### -output-buffer

The port driver formats the return data using an [**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md) structure that it stores in the buffer at **Irp->AssociatedIrp.SystemBuffer**.

The port driver stores the transferred data in the cache-aligned buffer pointed to by the **DataBuffer** member of [**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md).

The port driver fills the **CurrentTaskFile** member of [**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md) with the values present in the device's output registers at the completion of the ATA command. The application is responsible for interpreting the contents of the output registers to determine what errors, if any, were returned by the device.

### -output-buffer-length

The port driver updates the **DataTransferLength** member of the [**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md) structure to indicate the amount of data that was transferred from the device.

### -status-block

The **Information** member is set to the number of bytes returned in the output buffer at **Irp->AssociatedIrp.SystemBuffer**. The **Status** member is set to STATUS_SUCCESS or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INVALID_PARAMETER if the input **Length** value in [**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md) is improperly set.

## -see-also

[**ATA_PASS_THROUGH_DIRECT**](ns-ntddscsi-_ata_pass_through_direct.md)

[**IOCTL_ATA_PASS_THROUGH**](ni-ntddscsi-ioctl_ata_pass_through.md)
