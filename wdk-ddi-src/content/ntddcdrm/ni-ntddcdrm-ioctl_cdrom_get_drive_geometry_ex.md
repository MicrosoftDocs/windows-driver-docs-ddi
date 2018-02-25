---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
title: IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
author: windows-driver-content
description: Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older IOCTL_CDROM_GET_DRIVE_GEOMETRY request.
old-location: storage\ioctl_cdrom_get_drive_geometry_ex.htm
old-project: storage
ms.assetid: ef04ba90-698f-4ae2-9ac6-106d66b61080
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX, IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX control code [Storage Devices], k307_d92083df-7f01-4858-8bab-5b4b4ea5eaea.xml, ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX, storage.ioctl_cdrom_get_drive_geometry_ex
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_drive_geometry.md">IOCTL_CDROM_GET_DRIVE_GEOMETRY</a> request. The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT) partitioned media. However, IOCTL_CDROM_GET_DRIVE_GEOMETRY can read only MBR-style media.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>-type information in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the IO_STACK_LOCATION structure of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DISK_GEOMETRY_EX).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_UNRECOGNIZED_MEDIA, STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, or STATUS_BUFFER_TOO_SMALL.


## -remarks



TBD




## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

