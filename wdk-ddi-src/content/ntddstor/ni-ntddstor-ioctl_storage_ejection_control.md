---
UID: NI:ntddstor.IOCTL_STORAGE_EJECTION_CONTROL
title: IOCTL_STORAGE_EJECTION_CONTROL
author: windows-driver-content
description: Locks the device to prevent removal of the media.
old-location: storage\ioctl_storage_ejection_control.htm
old-project: storage
ms.assetid: 0b9726a1-0658-4eda-8f27-abf647cdc046
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_storage_ejection_control, IOCTL_STORAGE_EJECTION_CONTROL control code [Storage Devices], IOCTL_STORAGE_EJECTION_CONTROL, ntddstor/IOCTL_STORAGE_EJECTION_CONTROL, k307_fe4c03f1-b835-4c04-bb7b-4a8bd982dcc7.xml
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
-	IOCTL_STORAGE_EJECTION_CONTROL
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_EJECTION_CONTROL IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Locks the device to prevent removal of the media. If the driver can prevent the media from being removed while the drive is in use, the driver disables or enables the mechanism that ejects media, thereby locking the drive. A caller must open the device with FILE_READ_ATTRIBUTES to send this request. 

Unlike <a href="..\ntddstor\ni-ntddstor-ioctl_storage_media_removal.md">IOCTL_STORAGE_MEDIA_REMOVAL</a>, the driver tracks <b>IOCTL_STORAGE_EJECTION_CONTROL</b> requests by caller and ignores unlock requests for which it has not received a lock request from the same caller, thereby preventing other callers from unlocking the drive.

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
Under normal circumstances, the caller who locked the device using IOCTL_STORAGE_EJECTION_CONTROL, unlocks the device by sending IOCTL_STORAGE_EJECTION_CONTROL again with <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> set to a boolean value of <b>FALSE</b>. However, sometimes the caller fails to unlock the device properly. 

To ensure that media removal locks are released properly, the class driver keeps track of callers who lock the media with IOCTL_STORAGE_EJECTION_CONTROL. If the caller terminates without unlocking the device, the class driver unlocks the device.




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

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_eject_media.md">IOCTL_STORAGE_EJECT_MEDIA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_EJECTION_CONTROL control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

