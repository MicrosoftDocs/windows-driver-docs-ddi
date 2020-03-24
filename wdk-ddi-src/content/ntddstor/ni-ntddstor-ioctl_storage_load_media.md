---
UID: NI:ntddstor.IOCTL_STORAGE_LOAD_MEDIA
title: IOCTL_STORAGE_LOAD_MEDIA (ntddstor.h)
description: Causes media to be loaded in a device that the caller has opened for read or write access.
old-location: storage\ioctl_storage_load_media.htm
tech.root: storage
ms.assetid: 137ebbec-53f7-4bf6-b43b-2c736d66eb97
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_LOAD_MEDIA IOCTL"]
ms.keywords: IOCTL_STORAGE_LOAD_MEDIA, IOCTL_STORAGE_LOAD_MEDIA control, IOCTL_STORAGE_LOAD_MEDIA control code [Storage Devices], k307_730c4c03-9d36-406b-8965-270aa539d0ca.xml, ntddstor/IOCTL_STORAGE_LOAD_MEDIA, storage.ioctl_storage_load_media
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_LOAD_MEDIA"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_LOAD_MEDIA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_LOAD_MEDIA IOCTL


## -description



Causes media to be loaded in a device that the caller has opened for read or write access. If read or write access to the device is not necessary, the caller can improve performance by opening the device with FILE_READ_ATTRIBUTES and issuing an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_load_media2">IOCTL_STORAGE_LOAD_MEDIA2</a> request instead. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, STATUS_BUFFER_TOO_SMALL, or STATUS_DEVICE_NOT_CONNECTED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_load_media2">IOCTL_STORAGE_LOAD_MEDIA2</a>
 

 

