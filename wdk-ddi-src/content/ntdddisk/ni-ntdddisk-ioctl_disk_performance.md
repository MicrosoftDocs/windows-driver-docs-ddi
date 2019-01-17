---
UID: NI:ntdddisk.IOCTL_DISK_PERFORMANCE
title: IOCTL_DISK_PERFORMANCE
description: Increments a reference counter that enables the collection of disk performance statistics, such as the numbers of bytes read and written since the driver last processed this request, for a corresponding disk monitoring application.
old-location: storage\ioctl_disk_performance.htm
tech.root: storage
ms.assetid: d88d323d-6e74-4a4b-9246-893d92bea89b
ms.date: 03/29/2018
ms.keywords: IOCTL_DISK_PERFORMANCE, IOCTL_DISK_PERFORMANCE control, IOCTL_DISK_PERFORMANCE control code [Storage Devices], k307_f7ebe3b4-ed77-4c99-af07-c6639b5fd3be.xml, ntdddisk/IOCTL_DISK_PERFORMANCE, storage.ioctl_disk_performance
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_PERFORMANCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_PERFORMANCE IOCTL


## -description



Increments a reference counter that enables the collection of disk performance statistics, such as the numbers of bytes read and written since the driver last processed this request, for a corresponding disk monitoring application. In Microsoft Windows 2000 this IOCTL is handled by the filter driver diskperf. In Windows XP and later operating systems, the partition manager handles this request for disks and <i>ftdisk.sys </i>and <i>dmio.sys </i>handle this request for volumes. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552633">DISK_PERFORMANCE</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(DISK_PERFORMANCE).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(DISK_PERFORMANCE) when the <b>Status</b> field is set to STATUS_SUCCESS. Otherwise, the <b>Status</b> field can be set to STATUS_INVALID_PARAMETER or STATUS_BUFFER_TOO_SMALL. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560393">IOCTL_DISK_PERFORMANCE_OFF</a>
 

 

