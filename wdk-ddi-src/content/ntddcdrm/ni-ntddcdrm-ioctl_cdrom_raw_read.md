---
UID: NI:ntddcdrm.IOCTL_CDROM_RAW_READ
title: IOCTL_CDROM_RAW_READ
author: windows-driver-content
description: Reads data from the CD-ROM in raw mode.
old-location: storage\ioctl_cdrom_raw_read.htm
old-project: storage
ms.assetid: b7791cf7-476c-4319-976d-9da3d96b6a76
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_CDROM_RAW_READ, IOCTL_CDROM_RAW_READ control code [Storage Devices], k307_1c2f1a05-940c-40f8-a280-3a23d3bb4171.xml, ntddcdrm/IOCTL_CDROM_RAW_READ, storage.ioctl_cdrom_raw_read
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_RAW_READ
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_RAW_READ IOCTL


## -description



Reads data from the CD-ROM in raw mode.




## -ioctlparameters




### -input-buffer

If the IOCTL is from user mode, <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563958">RAW_READ_INFO</a> structure that specifies the starting disk offset, the sector count, and the track mode (XA or CDDA) for the read. <b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of the structure, which must be &gt;= <b>sizeof</b>(RAW_READ_INFO). <b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the size of the buffer to be read, which must be &gt;= <b>sizeof</b>(<i>SectorCount</i> * RAW_SECTOR_SIZE).

If the IOCTL is from kernel mode, <b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains a structure that specifies the starting disk offset, the sector count, and the track mode (XA or CDDA) for the read. <b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the size of the buffer, in bytes, to be read, which must be &gt;= <b>sizeof</b>(<i>SectorCount</i> * RAW_SECTOR_SIZE).


### -input-buffer-length

See above.


### -output-buffer

The driver writes the requested bytes directly (using DMA or PIO) to the buffer described by the MDL at <b>Irp-&gt;MdlAddress</b>.


### -output-buffer-length

Length of an MDL.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the read is successful, the driver sets <b>Status</b> to STATUS_SUCCESS and <b>Information</b> to the number of bytes transferred. If the read is not successful, the driver sets <b>Information</b> to zero and <b>Status</b> to possibly STATUS_INVALID_PARAMETER, STATUS_INSUFFICIENT_RESOURCES, or STATUS_INVALID_DEVICE_REQUEST. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563958">RAW_READ_INFO</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_RAW_READ control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

