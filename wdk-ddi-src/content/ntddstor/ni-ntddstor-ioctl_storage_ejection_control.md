---
UID: NI:ntddstor.IOCTL_STORAGE_EJECTION_CONTROL
title: IOCTL_STORAGE_EJECTION_CONTROL (ntddstor.h)
description: Locks the device to prevent removal of the media.
old-location: storage\ioctl_storage_ejection_control.htm
tech.root: storage
ms.assetid: 0b9726a1-0658-4eda-8f27-abf647cdc046
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_EJECTION_CONTROL, IOCTL_STORAGE_EJECTION_CONTROL control, IOCTL_STORAGE_EJECTION_CONTROL control code [Storage Devices], k307_fe4c03f1-b835-4c04-bb7b-4a8bd982dcc7.xml, ntddstor/IOCTL_STORAGE_EJECTION_CONTROL, storage.ioctl_storage_ejection_control
ms.topic: ioctl
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_EJECTION_CONTROL"
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
- IOCTL_STORAGE_EJECTION_CONTROL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_EJECTION_CONTROL IOCTL


## -description



Locks the device to prevent removal of the media. If the driver can prevent the media from being removed while the drive is in use, the driver disables or enables the mechanism that ejects media, thereby locking the drive. A caller must open the device with FILE_READ_ATTRIBUTES to send this request. 

Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_media_removal">IOCTL_STORAGE_MEDIA_REMOVAL</a>, the driver tracks <b>IOCTL_STORAGE_EJECTION_CONTROL</b> requests by caller and ignores unlock requests for which it has not received a lock request from the same caller, thereby preventing other callers from unlocking the drive.

A driver for a removable-media device - can support this IOCTL must do the following:

<ol>
<li>
Keep a lock count, tagged by caller, in the device object extension.

</li>
<li>
Keep the lock count per physical device.

</li>
<li>
When called with this IOCTL, if the flag to prevent removing the media is set, increment the count; if the flag is clear and the driver has previously received a lock request from the same caller, decrement the count.

</li>
<li>
Prevent removal of the media unless all lock counts are zero.

</li>
</ol>
Under normal circumstances, the caller who locked the device using IOCTL_STORAGE_EJECTION_CONTROL, unlocks the device by sending IOCTL_STORAGE_EJECTION_CONTROL again with <b>Irp->AssociatedIrp.SystemBuffer</b> set to a boolean value of <b>FALSE</b>. However, sometimes the caller fails to unlock the device properly. 

To ensure that media removal locks are released properly, the class driver keeps track of callers who lock the media with IOCTL_STORAGE_EJECTION_CONTROL. If the caller terminates without unlocking the device, the class driver unlocks the device.




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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_eject_media">IOCTL_STORAGE_EJECT_MEDIA</a>
 

 

