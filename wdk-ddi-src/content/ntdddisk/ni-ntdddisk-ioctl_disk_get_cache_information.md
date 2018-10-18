---
UID: NI:ntdddisk.IOCTL_DISK_GET_CACHE_INFORMATION
title: IOCTL_DISK_GET_CACHE_INFORMATION
author: windows-driver-content
description: Returns disk cache configuration data.
old-location: storage\ioctl_disk_get_cache_information.htm
tech.root: storage
ms.assetid: fc651954-2048-4358-91b0-4d99e38e9a67
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_GET_CACHE_INFORMATION, IOCTL_DISK_GET_CACHE_INFORMATION control, IOCTL_DISK_GET_CACHE_INFORMATION control code [Storage Devices], k307_1471eb7a-169f-4653-9bfe-01714d6299b7.xml, ntdddisk/IOCTL_DISK_GET_CACHE_INFORMATION, storage.ioctl_disk_get_cache_information
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
-	IOCTL_DISK_GET_CACHE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_GET_CACHE_INFORMATION IOCTL


## -description



Returns disk cache configuration data.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The device driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552580">DISK_CACHE_INFORMATION</a> in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL. 


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size of the block of status information being returned, <b>sizeof</b>(DISK_CACHE_INFORMATION). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DEVICE_NOT_READY, STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_NOT_SUPPORTED.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552580">DISK_CACHE_INFORMATION</a>
 

 

