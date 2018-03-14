---
UID: NI:ntdddisk.IOCTL_DISK_REASSIGN_BLOCKS_EX
title: IOCTL_DISK_REASSIGN_BLOCKS_EX
author: windows-driver-content
description: Maps defective blocks to a new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool.
old-location: storage\ioctl_disk_reassign_blocks_ex.htm
old-project: storage
ms.assetid: 885CC365-A730-4C1E-AD74-89D47DC17407
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DISK_REASSIGN_BLOCKS_EX, IOCTL_DISK_REASSIGN_BLOCKS_EX control code [Storage Devices], ntdddisk/IOCTL_DISK_REASSIGN_BLOCKS_EX, storage.ioctl_disk_reassign_blocks_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	IOCTL_DISK_REASSIGN_BLOCKS_EX
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_REASSIGN_BLOCKS_EX IOCTL


## -description



     Maps defective blocks to a new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool.  
    
   A <b>IOCTL_DISK_REASSIGN_BLOCKS_EX</b> request allows for a larger number of blocks for assignment than the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_reassign_blocks.md">IOCTL_DISK_REASSIGN_BLOCKS</a> request.


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_reassign_blocks_ex.md">REASSIGN_BLOCKS_EX</a> values to be set. Note that this structure contains a variable-sized array of block numbers. It is the caller's responsibility to make sure that the array of block numbers is sorted in ascending order.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(REASSIGN_BLOCKS_EX). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_reassign_blocks_ex.md">REASSIGN_BLOCKS_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_REASSIGN_BLOCKS_EX control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

