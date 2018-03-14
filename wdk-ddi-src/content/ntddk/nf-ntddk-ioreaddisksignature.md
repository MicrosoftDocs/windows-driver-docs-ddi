---
UID: NF:ntddk.IoReadDiskSignature
title: IoReadDiskSignature function
author: windows-driver-content
description: The IoReadDiskSignature routine reads the disk signature information for the partition table of a disk.
old-location: storage\ioreaddisksignature.htm
old-project: storage
ms.assetid: c56d767f-598c-46b8-bab1-ce4de0780076
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IoReadDiskSignature, IoReadDiskSignature routine [Storage Devices], ntddk/IoReadDiskSignature, rtns-disk_4bd8bcea-c43a-45ea-a074-013b8eb30e01.xml, storage.ioreaddisksignature
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
-	IoReadDiskSignature
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoReadDiskSignature function


## -description


The <b>IoReadDiskSignature</b> routine reads the disk signature information for the partition table of a disk.


## -syntax


````
NTSTATUS IoReadDiskSignature(
  _In_  PDEVICE_OBJECT  DeviceObject,
  _In_  ULONG           BytesPerSector,
  _Out_ PDISK_SIGNATURE Signature
);
````


## -parameters




### -param DeviceObject [in]

Specifies the device object for the disk to read.


### -param BytesPerSector [in]

Specifies the number of bytes per sector of the disk.


### -param Signature [out]

Pointer to a <a href="..\ntddk\ns-ntddk-_disk_signature.md">DISK_SIGNATURE</a> structure the routine uses to return the disk signature information.


## -returns



The routine returns STATUS_SUCCESS on success, or the appropriate error code on failure. The routine returns STATUS_DISK_CORRUPT_ERROR if it detects that the disk partition table is corrupted.




## -remarks



<b>IoReadDiskSignature</b> must only be used by disk drivers. Other drivers should use the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a> I/O request instead.




## -see-also

<a href="..\ntddk\ns-ntddk-_disk_signature.md">DISK_SIGNATURE</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a>



 

 


