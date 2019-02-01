---
UID: NI:ntdddisk.IOCTL_DISK_GET_DRIVE_GEOMETRY_EX
title: IOCTL_DISK_GET_DRIVE_GEOMETRY_EX (ntdddisk.h)
description: Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The difference between IOCTL_DISK_GET_DRIVE_GEOMETRY_EX and the older IOCTL_DISK_GET_DRIVE_GEOMETRY request is that IOCTL_DISK_GET_DRIVE_GEOMETRY_EX can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT)-type partitioned media, whereas IOCTL_DISK_GET_DRIVE_GEOMETRY can only read MBR-style media.
old-location: storage\ioctl_disk_get_drive_geometry_ex.htm
tech.root: storage
ms.assetid: c0cf6b73-3283-4a58-845a-79f3b078db46
ms.date: 03/29/2018
ms.keywords: IOCTL_DISK_GET_DRIVE_GEOMETRY_EX, IOCTL_DISK_GET_DRIVE_GEOMETRY_EX control, IOCTL_DISK_GET_DRIVE_GEOMETRY_EX control code [Storage Devices], k307_d20497cd-63a3-4e07-9920-b051d68841db.xml, ntdddisk/IOCTL_DISK_GET_DRIVE_GEOMETRY_EX, storage.ioctl_disk_get_drive_geometry_ex
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_GET_DRIVE_GEOMETRY_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_GET_DRIVE_GEOMETRY_EX IOCTL


## -description



Returns information about the physical disk's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

The difference between IOCTL_DISK_GET_DRIVE_GEOMETRY_EX and the older <a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> request is that IOCTL_DISK_GET_DRIVE_GEOMETRY_EX can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT)-type partitioned media, whereas IOCTL_DISK_GET_DRIVE_GEOMETRY can only read MBR-style media. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552618">DISK_GEOMETRY_EX</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The size of the output buffer may not be the same size as the input buffer.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least (<b>sizeof</b>(DISK_GEOMETRY) + <b>sizeof</b>(LARGE_INTEGER)) and up to (<b>sizeof</b>(DISK_GEOMETRY) + <b>sizeof</b>(LARGE_INTEGER) + <b>sizeof</b>(DISK_PARTITION_INFO) + <b>sizeof</b>(DISK_DETECTION_INFO)).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. 

The <b>Status</b> field returns one of the following values:

<ul>
<li><b>STATUS_SUCCESS</b></li>
<li><b>STATUS_UNRECOGNIZED_MEDIA</b></li>
<li><b>STATUS_INVALID_PARAMETER</b></li>
<li><b>STATUS_INVALID_DEVICE_REQUEST</b></li>
<li><b>STATUS_INFO_LENGTH_MISMATCH</b></li>
<li><b>STATUS_INSUFFICIENT_RESOURCES</b></li>
<li><b>STATUS_BUFFER_TOO_SMALL</b></li>
</ul>

## -remarks



Only callers above Partmgr.sys may call this IOCTL as it contains disk partition information. 

This IOCTL uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff560357">IOCTL_DISK_GET_DRIVE_GEOMETRY</a> to get the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552613">DISK_GEOMETRY</a> structure and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560370">IOCTL_DISK_GET_LENGTH_INFO</a> to get the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff554986">GET_LENGTH_INFORMATION</a> structure. Both of these IOCTL's are supported for use at the disk.sys level. 



