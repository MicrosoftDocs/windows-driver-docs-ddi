---
UID: NI:ntdddisk.IOCTL_DISK_VERIFY
title: IOCTL_DISK_VERIFY
author: windows-driver-content
description: Performs verification for a specified extent on a disk.
old-location: storage\ioctl_disk_verify.htm
old-project: storage
ms.assetid: 923a7fac-c1d5-4634-b209-087e3d5d217a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DISK_VERIFY, IOCTL_DISK_VERIFY control code [Storage Devices], k307_bafd5046-34ca-4e76-b1a6-bf5195adbb3b.xml, ntdddisk/IOCTL_DISK_VERIFY, storage.ioctl_disk_verify
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
-	IOCTL_DISK_VERIFY
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_VERIFY IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Performs verification for a specified extent on a disk. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_verify_information.md">VERIFY_INFORMATION</a> data specifying the starting offset and length to be verified. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(VERIFY_INFORMATION).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero to prevent the I/O manager from copying data from <b>SystemBuffer</b> back into the user area. 

If the request is successful, then the <b>Status</b> field is set to STATUS_SUCCESS. Otherwise, the <b>Status</b> field can be set to STATUS_BUFFER_TOO_SMALL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INVALID_PARAMETER, STATUS_INSUFFICIENT_RESOURCES, STATUS_NONEXISTENT_SECTOR, STATUS_DEVICE_DATA_ERROR, STATUS_INVALID_DEVICE_REQUEST, STATUS_IO_TIMEOUT, or STATUS_DEVICE_NOT_CONNECTED.


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_verify_information.md">VERIFY_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_VERIFY control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

