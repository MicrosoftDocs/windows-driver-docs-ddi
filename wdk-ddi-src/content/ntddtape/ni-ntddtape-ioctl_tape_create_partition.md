---
UID: NI:ntddtape.IOCTL_TAPE_CREATE_PARTITION
title: IOCTL_TAPE_CREATE_PARTITION
author: windows-driver-content
description: Creates the specified number of fixed, select, or initiator partition(s) of the given size on the media.
old-location: storage\ioctl_tape_create_partition.htm
old-project: storage
ms.assetid: da220281-a08d-4aeb-abb4-471aacb2461a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_TAPE_CREATE_PARTITION, IOCTL_TAPE_CREATE_PARTITION control code [Storage Devices], k307_d1911c51-33f1-4c45-bbf0-ace7714fa53f.xml, ntddtape/IOCTL_TAPE_CREATE_PARTITION, storage.ioctl_tape_create_partition
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
-	Ntddtape.h
api_name:
-	IOCTL_TAPE_CREATE_PARTITION
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_CREATE_PARTITION IOCTL


## -description



Creates the specified number of fixed, select, or initiator partition(s) of the given size on the media.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="..\ntddtape\ns-ntddtape-_tape_create_partition.md">TAPE_CREATE_PARTITION</a> that specifies the partition(s) to be created. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_CREATE_PARTITION). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED. 


## -see-also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="..\ntddtape\ns-ntddtape-_tape_create_partition.md">TAPE_CREATE_PARTITION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_CREATE_PARTITION control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

