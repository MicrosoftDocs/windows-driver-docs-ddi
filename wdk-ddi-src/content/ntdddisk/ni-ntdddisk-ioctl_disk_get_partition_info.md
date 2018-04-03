---
UID: NI:ntdddisk.IOCTL_DISK_GET_PARTITION_INFO
title: IOCTL_DISK_GET_PARTITION_INFO
author: windows-driver-content
description: Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_get_partition_info.htm
old-project: storage
ms.assetid: 4ac10da1-955e-471d-9d99-64f48e3c96a7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_GET_PARTITION_INFO, IOCTL_DISK_GET_PARTITION_INFO control code [Storage Devices], k307_6643c9ae-b43e-44a9-b1ca-4963c170b9d1.xml, ntdddisk/IOCTL_DISK_GET_PARTITION_INFO, storage.ioctl_disk_get_partition_info
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
-	IOCTL_DISK_GET_PARTITION_INFO
product:
- Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_GET_PARTITION_INFO IOCTL


## -description



Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.)




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(PARTITION_INFORMATION).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a>
 

 

