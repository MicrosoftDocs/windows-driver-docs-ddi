---
UID: NI:ntdddisk.IOCTL_DISK_REASSIGN_BLOCKS
title: IOCTL_DISK_REASSIGN_BLOCKS
author: windows-driver-content
description: Maps defective blocks to new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool.
old-location: storage\ioctl_disk_reassign_blocks.htm
old-project: storage
ms.assetid: d79f8e47-87c5-4203-b9d7-722d9be4e848
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_REASSIGN_BLOCKS, IOCTL_DISK_REASSIGN_BLOCKS control code [Storage Devices], k307_56b4bc99-0b59-48d5-a87d-277ee06a0830.xml, ntdddisk/IOCTL_DISK_REASSIGN_BLOCKS, storage.ioctl_disk_reassign_blocks
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
-	IOCTL_DISK_REASSIGN_BLOCKS
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_REASSIGN_BLOCKS IOCTL


## -description



Maps defective blocks to new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563962">REASSIGN_BLOCKS</a> values to be set. Note that this structure contains a variable-sized array of block numbers. It is the caller's responsibility to make sure that the array of block numbers is sorted in ascending order.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(REASSIGN_BLOCKS). 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563962">REASSIGN_BLOCKS</a>
 

 

