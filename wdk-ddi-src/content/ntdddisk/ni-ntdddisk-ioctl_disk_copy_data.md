---
UID: NI:ntdddisk.IOCTL_DISK_COPY_DATA
title: IOCTL_DISK_COPY_DATA (ntdddisk.h)
description: This IOCTL_DISK_COPY_DATA IOCTL is used to copy data from one area of the disk to another.
old-location: storage\ioctl_disk_copy_data.htm
tech.root: storage
ms.assetid: 1434ee49-4c3d-4104-bca4-c0ea4299c9aa
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_COPY_DATA IOCTL"]
ms.keywords: IOCTL_DISK_COPY_DATA, IOCTL_DISK_COPY_DATA control, IOCTL_DISK_COPY_DATA control code [Storage Devices], k307_d7859abc-a32a-4930-b612-6bea53331e3a.xml, ntdddisk/IOCTL_DISK_COPY_DATA, storage.ioctl_disk_copy_data
f1_keywords:
 - "ntdddisk/IOCTL_DISK_COPY_DATA"
 - "IOCTL_DISK_COPY_DATA"
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
- IOCTL_DISK_COPY_DATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_COPY_DATA IOCTL


## -description



This IOCTL_DISK_COPY_DATA IOCTL is used to copy data from one area of the disk to another.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_copy_data_parameters">DISK_COPY_DATA_PARAMETERS</a> data. <b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS if the operation is successful.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_copy_data_parameters">DISK_COPY_DATA_PARAMETERS</a>
 

 

