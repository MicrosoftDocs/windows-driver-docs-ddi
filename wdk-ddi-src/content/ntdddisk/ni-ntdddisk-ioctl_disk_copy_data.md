---
UID: NI:ntdddisk.IOCTL_DISK_COPY_DATA
title: IOCTL_DISK_COPY_DATA
author: windows-driver-content
description: This IOCTL_DISK_COPY_DATA IOCTL is used to copy data from one area of the disk to another.
old-location: storage\ioctl_disk_copy_data.htm
old-project: storage
ms.assetid: 1434ee49-4c3d-4104-bca4-c0ea4299c9aa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_DISK_COPY_DATA, IOCTL_DISK_COPY_DATA control code [Storage Devices], k307_d7859abc-a32a-4930-b612-6bea53331e3a.xml, ntdddisk/IOCTL_DISK_COPY_DATA, storage.ioctl_disk_copy_data
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IOCTL_DISK_COPY_DATA
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_COPY_DATA IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



This IOCTL_DISK_COPY_DATA IOCTL is used to copy data from one area of the disk to another.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_disk_copy_data_parameters.md">DISK_COPY_DATA_PARAMETERS</a> data. <b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS if the operation is successful.


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_disk_copy_data_parameters.md">DISK_COPY_DATA_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_COPY_DATA control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

