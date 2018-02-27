---
UID: NI:ntddstor.IOCTL_STORAGE_MEDIA_REMOVAL
title: IOCTL_STORAGE_MEDIA_REMOVAL
author: windows-driver-content
description: Locks the device to prevent removal of the media.
old-location: storage\ioctl_storage_media_removal.htm
old-project: storage
ms.assetid: ea8d7924-7ecc-47df-9616-8e2ed60c3de8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_STORAGE_MEDIA_REMOVAL, IOCTL_STORAGE_MEDIA_REMOVAL control code [Storage Devices], k307_3579b0fa-49fa-4051-8726-15662992f0d2.xml, ntddstor/IOCTL_STORAGE_MEDIA_REMOVAL, storage.ioctl_storage_media_removal
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
-	IOCTL_STORAGE_MEDIA_REMOVAL
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_MEDIA_REMOVAL IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Locks the device to prevent removal of the media. If the driver can prevent the media from being removed while the drive is in use, it disables or enables the mechanism that ejects media on a device - the caller has opened for read or write access.

Unlike <a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>, for which the driver tracks requests by caller, the driver ignores IOCTL_STORAGE_MEDIA_REMOVAL unlock requests only if its lock count is already zero, thereby allowing any caller to unlock the drive.

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

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a Boolean value, with <b>TRUE</b> indicating that the driver should lock the media in the drive.


### -input-buffer-length

The length of a Boolean.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_DEVICE_NOT_CONNECTED.


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_MEDIA_REMOVAL control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

