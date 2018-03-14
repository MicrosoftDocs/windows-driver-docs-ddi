---
UID: NF:ntddk.IoCreateDisk
title: IoCreateDisk function
author: windows-driver-content
description: The IoCreateDisk routine initializes a raw disk by creating a new partition table.
old-location: storage\iocreatedisk.htm
old-project: storage
ms.assetid: 0ad85551-a8d2-4f7f-958b-fe23111de340
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IoCreateDisk, IoCreateDisk routine [Storage Devices], ntddk/IoCreateDisk, rtns-disk_5f69686f-f812-4ccc-8bc8-4caa70230d20.xml, storage.iocreatedisk
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: This routine is only available on Windows XP and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCreateDisk
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoCreateDisk function


## -description


The <b>IoCreateDisk</b> routine initializes a raw disk by creating a new partition table.


## -syntax


````
NTSTATUS IoCreateDisk(
  _In_     PDEVICE_OBJECT      DeviceObject,
  _In_opt_ struct _CREATE_DISK *Disk
);
````


## -parameters




### -param DeviceObject [in]

Specifies the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> for the raw disk.


### -param Disk [in, optional]

Pointer to a <a href="..\ntdddisk\ns-ntdddisk-_create_disk.md">CREATE_DISK</a> structure that specifies the type and parameters for the partition table. If <i>Disk</i> is <b>NULL</b>, the routine deletes the partition table on the disk.


## -returns



Returns STATUS_SUCCESS on success, or the appropriate error code on failure.




## -remarks



<b>IoCreateDisk</b> must only be used by disk drivers. Other drivers should use the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a> I/O request instead.




## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_create_disk.md">CREATE_DISK</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_create_disk.md">IOCTL_DISK_CREATE_DISK</a>



 

 


