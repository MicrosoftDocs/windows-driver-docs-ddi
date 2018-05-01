---
UID: NI:ntddstor.IOCTL_STORAGE_EJECT_MEDIA
title: IOCTL_STORAGE_EJECT_MEDIA
author: windows-driver-content
description: Causes the device to eject the media if the device supports ejection capabilities.
old-location: storage\ioctl_storage_eject_media.htm
old-project: storage
ms.assetid: 094edf6d-276b-4aae-9e60-52e181268e7d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_EJECT_MEDIA, IOCTL_STORAGE_EJECT_MEDIA control, IOCTL_STORAGE_EJECT_MEDIA control code [Storage Devices], k307_19063683-2dc1-4ce2-ac53-7754eee2562b.xml, ntddstor/IOCTL_STORAGE_EJECT_MEDIA, storage.ioctl_storage_eject_media
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_EJECT_MEDIA
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_EJECT_MEDIA IOCTL


## -description



Causes the device to eject the media if the device supports ejection capabilities.




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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_NO_MEDIA_IN_DEVICE or STATUS_INVALID_DEVICE_REQUEST.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560540">IOCTL_STORAGE_EJECTION_CONTROL</a>
 

 

