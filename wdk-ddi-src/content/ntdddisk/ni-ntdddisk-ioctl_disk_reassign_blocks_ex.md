---
UID: NI:ntdddisk.IOCTL_DISK_REASSIGN_BLOCKS_EX
title: IOCTL_DISK_REASSIGN_BLOCKS_EX (ntdddisk.h)
description: Maps defective blocks to a new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool.
old-location: storage\ioctl_disk_reassign_blocks_ex.htm
tech.root: storage
ms.assetid: 885CC365-A730-4C1E-AD74-89D47DC17407
ms.date: 03/29/2018
ms.keywords: IOCTL_DISK_REASSIGN_BLOCKS_EX, IOCTL_DISK_REASSIGN_BLOCKS_EX control, IOCTL_DISK_REASSIGN_BLOCKS_EX control code [Storage Devices], ntdddisk/IOCTL_DISK_REASSIGN_BLOCKS_EX, storage.ioctl_disk_reassign_blocks_ex
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntdddisk.h
api_name:
- IOCTL_DISK_REASSIGN_BLOCKS_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_REASSIGN_BLOCKS_EX IOCTL


## -description



     Maps defective blocks to a new location on disk. This request instructs the device to reassign the bad block address to a good block from its spare-block pool.  
    
   A <b>IOCTL_DISK_REASSIGN_BLOCKS_EX</b> request allows for a larger number of blocks for assignment than the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560398">IOCTL_DISK_REASSIGN_BLOCKS</a> request.


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/jj602804">REASSIGN_BLOCKS_EX</a> values to be set. Note that this structure contains a variable-sized array of block numbers. It is the caller's responsibility to make sure that the array of block numbers is sorted in ascending order.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(REASSIGN_BLOCKS_EX). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj602804">REASSIGN_BLOCKS_EX</a>
 

 

