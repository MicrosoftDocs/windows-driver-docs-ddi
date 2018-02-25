---
UID: NI:ntddcdvd.IOCTL_DVD_SEND_KEY
title: IOCTL_DVD_SEND_KEY
author: windows-driver-content
description: Sends the specified key to a DVD device to complete the related step in an authentication sequence.This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration.
old-location: storage\ioctl_dvd_send_key.htm
old-project: storage
ms.assetid: 8db0e6fe-1dfc-4f26-8fd7-7d170c33da0a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_DVD_SEND_KEY, IOCTL_DVD_SEND_KEY control code [Storage Devices], k307_9c0512f6-da79-4da0-a779-5a870ffe4b91.xml, ntddcdvd/IOCTL_DVD_SEND_KEY, storage.ioctl_dvd_send_key
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	Ntddcdvd.h
apiname:
-	IOCTL_DVD_SEND_KEY
product: Windows
targetos: Windows
req.typenames: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# IOCTL_DVD_SEND_KEY IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Sends the specified key to a DVD device to complete the related step in an authentication sequence.

This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration. Therefore, this request is limited to sending key types <b>DvdChallengeKey</b>, <b>DvdBusKey2</b>, and <b>DvdInvalidateAGID</b>. 

The <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_send_key2.md">IOCTL_DVD_SEND_KEY2</a> request has write access to the device and is not limited to these three key types. 

For more information, see <a href="..\ntddcdvd\ne-ntddcdvd-dvd_key_type.md">DVD_KEY_TYPE</a>.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a> structure that indicates the session ID, key type, and key to be sent to the device.


### -input-buffer-length

Length of a <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DVD_SEND_KEY control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

