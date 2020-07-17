---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
title: IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX (ntddcdrm.h)
description: Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older IOCTL_CDROM_GET_DRIVE_GEOMETRY request.
old-location: storage\ioctl_cdrom_get_drive_geometry_ex.htm
tech.root: storage
ms.assetid: ef04ba90-698f-4ae2-9ac6-106d66b61080
ms.date: 03/29/2018
keywords: ["IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX IOCTL"]
ms.keywords: IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX, IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX control, IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX control code [Storage Devices], k307_d92083df-7f01-4858-8bab-5b4b4ea5eaea.xml, ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX, storage.ioctl_cdrom_get_drive_geometry_ex
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX"
 - "IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX"
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
- IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX IOCTL


## -description



Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_drive_geometry">IOCTL_CDROM_GET_DRIVE_GEOMETRY</a> request. The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT) partitioned media. However, IOCTL_CDROM_GET_DRIVE_GEOMETRY can read only MBR-style media.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry_ex">DISK_GEOMETRY_EX</a>-type information in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the IO_STACK_LOCATION structure of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(DISK_GEOMETRY_EX).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_UNRECOGNIZED_MEDIA, STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, or STATUS_BUFFER_TOO_SMALL.


## -remarks



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry_ex">DISK_GEOMETRY_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_get_drive_geometry_ex">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a>
 

 

