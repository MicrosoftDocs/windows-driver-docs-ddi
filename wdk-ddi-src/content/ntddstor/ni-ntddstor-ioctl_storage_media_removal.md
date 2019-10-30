---
UID: NI:ntddstor.IOCTL_STORAGE_MEDIA_REMOVAL
title: IOCTL_STORAGE_MEDIA_REMOVAL (ntddstor.h)
description: Locks the device to prevent removal of the media.
old-location: storage\ioctl_storage_media_removal.htm
tech.root: storage
ms.assetid: ea8d7924-7ecc-47df-9616-8e2ed60c3de8
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_MEDIA_REMOVAL, IOCTL_STORAGE_MEDIA_REMOVAL control, IOCTL_STORAGE_MEDIA_REMOVAL control code [Storage Devices], k307_3579b0fa-49fa-4051-8726-15662992f0d2.xml, ntddstor/IOCTL_STORAGE_MEDIA_REMOVAL, storage.ioctl_storage_media_removal
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_MEDIA_REMOVAL"
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
- IOCTL_STORAGE_MEDIA_REMOVAL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_MEDIA_REMOVAL IOCTL


## -description



Locks the device to prevent removal of the media. If the driver can prevent the media from being removed while the drive is in use, it disables or enables the mechanism that ejects media on a device - the caller has opened for read or write access.

Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_ejection_control">IOCTL_STORAGE_EJECTION_CONTROL</a>, for which the driver tracks requests by caller, the driver ignores IOCTL_STORAGE_MEDIA_REMOVAL unlock requests only if its lock count is already zero, thereby allowing any caller to unlock the drive.

A driver for such a removable-media device that can support this IOCTL must do the following:

<ol>
<li>
Keep a lock count in the device object extension.

</li>
<li>
Keep the lock count per physical device.

</li>
<li>
When called with this IOCTL, if the flag to prevent removing the media is set, increment the count; if the flag is clear, decrement the count.

</li>
<li>
Prevent removal of the media unless all lock counts are zero.

</li>
</ol>



## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a Boolean value, with <b>TRUE</b> indicating that the driver should lock the media in the drive.


### -input-buffer-length

The length of a Boolean.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_DEVICE_NOT_CONNECTED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_ejection_control">IOCTL_STORAGE_EJECTION_CONTROL</a>
 

 

