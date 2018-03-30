---
UID: NI:ntdddisk.IOCTL_DISK_SET_DRIVE_LAYOUT
title: IOCTL_DISK_SET_DRIVE_LAYOUT
author: windows-driver-content
description: Repartitions a disk as specified. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_set_drive_layout.htm
old-project: storage
ms.assetid: d6b0682a-bce2-40d3-a69b-cf676c21d253
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DISK_SET_DRIVE_LAYOUT, IOCTL_DISK_SET_DRIVE_LAYOUT control code [Storage Devices], k307_53d3cc3b-a829-432a-8ee0-9a2035d08a62.xml, ntdddisk/IOCTL_DISK_SET_DRIVE_LAYOUT, storage.ioctl_disk_set_drive_layout
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
-	IOCTL_DISK_SET_DRIVE_LAYOUT
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_SET_DRIVE_LAYOUT IOCTL


## -description



Repartitions a disk as specified. (Floppy drivers need not handle this request.)




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a> values to be set. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DRIVE_LAYOUT_INFORMATION).


### -output-buffer

Returns updated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a>, possibly with modified partition numbers, to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned information. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a>
 

 

