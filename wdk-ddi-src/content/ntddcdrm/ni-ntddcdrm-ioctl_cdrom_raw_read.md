---
UID: NI:ntddcdrm.IOCTL_CDROM_RAW_READ
title: IOCTL_CDROM_RAW_READ (ntddcdrm.h)
description: Reads data from the CD-ROM in raw mode.
old-location: storage\ioctl_cdrom_raw_read.htm
tech.root: storage
ms.assetid: b7791cf7-476c-4319-976d-9da3d96b6a76
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_RAW_READ, IOCTL_CDROM_RAW_READ control, IOCTL_CDROM_RAW_READ control code [Storage Devices], k307_1c2f1a05-940c-40f8-a280-3a23d3bb4171.xml, ntddcdrm/IOCTL_CDROM_RAW_READ, storage.ioctl_cdrom_raw_read
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
- ntddcdrm.h
api_name:
- IOCTL_CDROM_RAW_READ
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_RAW_READ IOCTL


## -description



Reads data from the CD-ROM in raw mode.




## -ioctlparameters




### -input-buffer

If the IOCTL is from user mode, <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563958">RAW_READ_INFO</a> structure that specifies the starting disk offset, the sector count, and the track mode (XA or CDDA) for the read. <b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of the structure, which must be >= <b>sizeof</b>(RAW_READ_INFO). <b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the size of the buffer to be read, which must be >= <b>sizeof</b>(<i>SectorCount</i> * RAW_SECTOR_SIZE).

If the IOCTL is from kernel mode, <b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains a structure that specifies the starting disk offset, the sector count, and the track mode (XA or CDDA) for the read. <b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the size of the buffer, in bytes, to be read, which must be >= <b>sizeof</b>(<i>SectorCount</i> * RAW_SECTOR_SIZE).


### -input-buffer-length

See above.


### -output-buffer

The driver writes the requested bytes directly (using DMA or PIO) to the buffer described by the MDL at <b>Irp->MdlAddress</b>.


### -output-buffer-length

Length of an MDL.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the read is successful, the driver sets <b>Status</b> to STATUS_SUCCESS and <b>Information</b> to the number of bytes transferred. If the read is not successful, the driver sets <b>Information</b> to zero and <b>Status</b> to possibly STATUS_INVALID_PARAMETER, STATUS_INSUFFICIENT_RESOURCES, or STATUS_INVALID_DEVICE_REQUEST. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563958">RAW_READ_INFO</a>
 

 

