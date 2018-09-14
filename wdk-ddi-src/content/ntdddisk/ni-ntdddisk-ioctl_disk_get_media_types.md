---
UID: NI:ntdddisk.IOCTL_DISK_GET_MEDIA_TYPES
title: IOCTL_DISK_GET_MEDIA_TYPES
author: windows-driver-content
description: In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_GET_MEDIA_TYPES. The only difference between the two IOCTLs is the base value.
old-location: storage\ioctl_disk_get_media_types.htm
tech.root: storage
ms.assetid: d6e6cd4c-680d-4885-b910-3de8de143e2b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_GET_MEDIA_TYPES, IOCTL_DISK_GET_MEDIA_TYPES control, IOCTL_DISK_GET_MEDIA_TYPES control code [Storage Devices], k307_692b21f7-7d14-4ba9-9d56-381606f5f5b1.xml, ntdddisk/IOCTL_DISK_GET_MEDIA_TYPES, storage.ioctl_disk_get_media_types
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header:
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
-	ntdddisk.h
api_name:
-	IOCTL_DISK_GET_MEDIA_TYPES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_GET_MEDIA_TYPES IOCTL


## -description


In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560559">IOCTL_STORAGE_GET_MEDIA_TYPES</a>. The only difference between the two IOCTLs is the base value.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).



