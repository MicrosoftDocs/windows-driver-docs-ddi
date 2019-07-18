---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_DRIVE_GEOMETRY
title: IOCTL_CDROM_GET_DRIVE_GEOMETRY (ntddcdrm.h)
description: Returns information about the CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).
old-location: storage\ioctl_cdrom_get_drive_geometry.htm
tech.root: storage
ms.assetid: ed9738cb-7016-417b-baae-b8d4242a384e
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_GET_DRIVE_GEOMETRY, IOCTL_CDROM_GET_DRIVE_GEOMETRY control, IOCTL_CDROM_GET_DRIVE_GEOMETRY control code [Storage Devices], k307_f082c6e5-9d9a-4a11-a363-710f30cf3881.xml, ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY, storage.ioctl_cdrom_get_drive_geometry
ms.topic: ioctl
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY"
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
- IOCTL_CDROM_GET_DRIVE_GEOMETRY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_DRIVE_GEOMETRY IOCTL


## -description



Returns information about the CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a>-type information in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(DISK_GEOMETRY).


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_drive_geometry_ex">IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX</a>
 

 

