---
UID: NI:ntdddisk.IOCTL_DISK_GET_LENGTH_INFO
title: IOCTL_DISK_GET_LENGTH_INFO
author: windows-driver-content
description: Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request.
old-location: storage\ioctl_disk_get_length_info.htm
old-project: storage
ms.assetid: 62d31b13-bc4a-4b2f-82be-551a61cae218
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_disk_get_length_info, IOCTL_DISK_GET_LENGTH_INFO control code [Storage Devices], IOCTL_DISK_GET_LENGTH_INFO, ntdddisk/IOCTL_DISK_GET_LENGTH_INFO, k307_50fea771-4937-481d-9a1b-f4d69bb939bb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntdddisk.h
apiname:
-	IOCTL_DISK_GET_LENGTH_INFO
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_GET_LENGTH_INFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="..\ntdddisk\ns-ntdddisk-_get_length_information.md">GET_LENGTH_INFORMATION</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(GET_LENGTH_INFORMATION). 


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or to STATUS_BUFFER_TOO_SMALL if the buffer supplied by the caller is inadequate. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_get_length_information.md">GET_LENGTH_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_GET_LENGTH_INFO control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

