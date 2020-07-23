---
UID: NI:ntdddisk.IOCTL_DISK_UPDATE_DRIVE_SIZE
title: IOCTL_DISK_UPDATE_DRIVE_SIZE (ntdddisk.h)
description: Updates device extension with drive size information for current media.
old-location: storage\ioctl_disk_update_drive_size.htm
tech.root: storage
ms.assetid: a12c1082-c3ff-40b8-b756-be320ab98b30
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_UPDATE_DRIVE_SIZE IOCTL"]
ms.keywords: IOCTL_DISK_UPDATE_DRIVE_SIZE, IOCTL_DISK_UPDATE_DRIVE_SIZE control, IOCTL_DISK_UPDATE_DRIVE_SIZE control code [Storage Devices], k307_52e1c8fb-a16b-41a6-a9bc-e0daec91f639.xml, ntdddisk/IOCTL_DISK_UPDATE_DRIVE_SIZE, storage.ioctl_disk_update_drive_size
f1_keywords:
 - "ntdddisk/IOCTL_DISK_UPDATE_DRIVE_SIZE"
 - "IOCTL_DISK_UPDATE_DRIVE_SIZE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntdddisk.h
api_name:
- IOCTL_DISK_UPDATE_DRIVE_SIZE
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_UPDATE_DRIVE_SIZE IOCTL


## -description



Updates device extension with drive size information for current media.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer


       Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL.

The device driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a> structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be >= <b>sizeof</b>(DISK_GEOMETRY). 


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry">DISK_GEOMETRY</a>
 

 

