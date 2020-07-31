---
UID: NI:ntdddisk.IOCTL_DISK_CONTROLLER_NUMBER
title: IOCTL_DISK_CONTROLLER_NUMBER (ntdddisk.h)
description: Retrieves the controller number and disk number for an IDE disk.
old-location: storage\ioctl_disk_controller_number.htm
tech.root: storage
ms.assetid: dbf7829b-c5b9-4428-a296-34199a726ec5
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_CONTROLLER_NUMBER IOCTL"]
ms.keywords: IOCTL_DISK_CONTROLLER_NUMBER, IOCTL_DISK_CONTROLLER_NUMBER control, IOCTL_DISK_CONTROLLER_NUMBER control code [Storage Devices], k307_227ab511-78ff-4aba-be29-3429329d05e5.xml, ntdddisk/IOCTL_DISK_CONTROLLER_NUMBER, storage.ioctl_disk_controller_number
f1_keywords:
 - "ntdddisk/IOCTL_DISK_CONTROLLER_NUMBER"
 - "IOCTL_DISK_CONTROLLER_NUMBER"
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
- IOCTL_DISK_CONTROLLER_NUMBER
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_CONTROLLER_NUMBER IOCTL


## -description



Retrieves the controller number and disk number for an IDE disk.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_controller_number">DISK_CONTROLLER_NUMBER</a> data.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the IO_STACK_LOCATION structure of the IRP indicates the size, in bytes, of the output buffer, which must be >= <b>sizeof</b>(DISK_CONTROLLER_NUMBER).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(DISK_CONTROLLER_NUMBER).

The <b>Status</b> field is set to STATUS_SUCCESS if the operation is successful. One possible status value is STATUS_BUFFER_TOO_SMALL if the output buffer provided by the caller is too small. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_controller_number">DISK_CONTROLLER_NUMBER</a>
 

 

