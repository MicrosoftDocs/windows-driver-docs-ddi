---
UID: NI:ntdddisk.IOCTL_DISK_FIND_NEW_DEVICES
title: IOCTL_DISK_FIND_NEW_DEVICES (ntdddisk.h)
description: In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_FIND_NEW_DEVICES. The only difference between the two IOCTLs is the base value.
old-location: storage\ioctl_disk_find_new_devices.htm
tech.root: storage
ms.assetid: d8a603a3-fa3c-4524-89f8-eed43d0db316
ms.date: 03/29/2018
ms.keywords: IOCTL_DISK_FIND_NEW_DEVICES, IOCTL_DISK_FIND_NEW_DEVICES control, IOCTL_DISK_FIND_NEW_DEVICES control code [Storage Devices], k307_369ae687-ba0c-4626-bd33-eb299ab4c2cd.xml, ntdddisk/IOCTL_DISK_FIND_NEW_DEVICES, storage.ioctl_disk_find_new_devices
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
-	IOCTL_DISK_FIND_NEW_DEVICES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_FIND_NEW_DEVICES IOCTL


## -description


In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560546">IOCTL_STORAGE_FIND_NEW_DEVICES</a>. The only difference between the two IOCTLs is the base value.


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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).



