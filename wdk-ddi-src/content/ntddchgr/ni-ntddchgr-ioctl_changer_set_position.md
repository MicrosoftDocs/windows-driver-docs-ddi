---
UID: NI:ntddchgr.IOCTL_CHANGER_SET_POSITION
title: IOCTL_CHANGER_SET_POSITION
author: windows-driver-content
description: Sets the changer's robotic transport mechanism to the specified element address, typically to optimize moving or exchanging media by positioning the transport beforehand.
old-location: storage\ioctl_changer_set_position.htm
tech.root: storage
ms.assetid: cd4f5872-d2cb-42ee-b78c-6b7d48d41e34
ms.date: 03/29/2018
ms.keywords: IOCTL_CHANGER_SET_POSITION, IOCTL_CHANGER_SET_POSITION control, IOCTL_CHANGER_SET_POSITION control code [Storage Devices], k307_f4580e0a-0f44-4c7f-9d89-81fe6db548c6.xml, ntddchgr/IOCTL_CHANGER_SET_POSITION, storage.ioctl_changer_set_position
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_SET_POSITION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_SET_POSITION IOCTL


## -description



Sets the changer's robotic transport mechanism to the specified element address, typically to optimize moving or exchanging media by positioning the transport beforehand.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551482">CHANGER_SET_POSITION</a> structure that specifies the transport to move and the destination. If the <b>Flip</b> member is <b>TRUE</b> and the device supports two-sided media, the media currently carried by the transport should be flipped. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_SET_POSITION). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_SET_POSITION). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_INVALID_PARAMETER. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551482">CHANGER_SET_POSITION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551449">ChangerSetPosition</a>
 

 

