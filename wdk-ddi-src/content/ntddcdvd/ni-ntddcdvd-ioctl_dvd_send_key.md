---
UID: NI:ntddcdvd.IOCTL_DVD_SEND_KEY
title: IOCTL_DVD_SEND_KEY
author: windows-driver-content
description: Sends the specified key to a DVD device to complete the related step in an authentication sequence.This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration.
old-location: storage\ioctl_dvd_send_key.htm
old-project: storage
ms.assetid: 8db0e6fe-1dfc-4f26-8fd7-7d170c33da0a
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdvd.h
api_name:
-	IOCTL_DVD_SEND_KEY
product:
- Windows
targetos: Windows
req.typenames: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# IOCTL_DVD_SEND_KEY IOCTL


## -description



Sends the specified key to a DVD device to complete the related step in an authentication sequence.

This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration. Therefore, this request is limited to sending key types <b>DvdChallengeKey</b>, <b>DvdBusKey2</b>, and <b>DvdInvalidateAGID</b>. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560429">IOCTL_DVD_SEND_KEY2</a> request has write access to the device and is not limited to these three key types. 

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553731">DVD_KEY_TYPE</a>.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a> structure that indicates the session ID, key type, and key to be sent to the device.


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a>.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a>
 

 

