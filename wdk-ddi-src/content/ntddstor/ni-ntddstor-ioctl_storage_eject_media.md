---
UID: NI:ntddstor.IOCTL_STORAGE_EJECT_MEDIA
title: IOCTL_STORAGE_EJECT_MEDIA
author: windows-driver-content
description: Causes the device to eject the media if the device supports ejection capabilities.
old-location: storage\ioctl_storage_eject_media.htm
old-project: storage
ms.assetid: 094edf6d-276b-4aae-9e60-52e181268e7d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_eject_media, IOCTL_STORAGE_EJECT_MEDIA control code [Storage Devices], IOCTL_STORAGE_EJECT_MEDIA, ntddstor/IOCTL_STORAGE_EJECT_MEDIA, k307_19063683-2dc1-4ce2-ac53-7754eee2562b.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddstor.h
apiname: 
-	IOCTL_STORAGE_EJECT_MEDIA
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_EJECT_MEDIA IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_EJECT_MEDIA control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

