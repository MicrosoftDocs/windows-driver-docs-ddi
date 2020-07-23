---
UID: NI:ntdddisk.IOCTL_DISK_GET_LENGTH_INFO
title: IOCTL_DISK_GET_LENGTH_INFO (ntdddisk.h)
description: Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request.
old-location: storage\ioctl_disk_get_length_info.htm
tech.root: storage
ms.assetid: 62d31b13-bc4a-4b2f-82be-551a61cae218
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GET_LENGTH_INFO IOCTL"]
ms.keywords: IOCTL_DISK_GET_LENGTH_INFO, IOCTL_DISK_GET_LENGTH_INFO control, IOCTL_DISK_GET_LENGTH_INFO control code [Storage Devices], k307_50fea771-4937-481d-9a1b-f4d69bb939bb.xml, ntdddisk/IOCTL_DISK_GET_LENGTH_INFO, storage.ioctl_disk_get_length_info
f1_keywords:
 - "ntdddisk/IOCTL_DISK_GET_LENGTH_INFO"
 - "IOCTL_DISK_GET_LENGTH_INFO"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows XP and later operating systems.
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
- IOCTL_DISK_GET_LENGTH_INFO
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_GET_LENGTH_INFO IOCTL


## -description



Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_get_length_information">GET_LENGTH_INFORMATION</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(GET_LENGTH_INFORMATION). 


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or to STATUS_BUFFER_TOO_SMALL if the buffer supplied by the caller is inadequate. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_get_length_information">GET_LENGTH_INFORMATION</a>
 

 

