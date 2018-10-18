---
UID: NI:ntddtape.IOCTL_TAPE_SET_MEDIA_PARAMS
title: IOCTL_TAPE_SET_MEDIA_PARAMS
author: windows-driver-content
description: Resets the block size of the media in the drive.
old-location: storage\ioctl_tape_set_media_params.htm
tech.root: storage
ms.assetid: c1411e72-84b4-4021-bed6-17308415be3a
ms.date: 3/29/2018
ms.keywords: IOCTL_TAPE_SET_MEDIA_PARAMS, IOCTL_TAPE_SET_MEDIA_PARAMS control, IOCTL_TAPE_SET_MEDIA_PARAMS control code [Storage Devices], k307_c549601d-5c5e-452b-8880-844820207215.xml, ntddtape/IOCTL_TAPE_SET_MEDIA_PARAMS, storage.ioctl_tape_set_media_params
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
-	Ntddtape.h
api_name:
-	IOCTL_TAPE_SET_MEDIA_PARAMS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_SET_MEDIA_PARAMS IOCTL


## -description



Resets the block size of the media in the drive.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567973">TAPE_SET_MEDIA_PARAMETERS</a> structure containing the block size to be set. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_SET_MEDIA_PARAMETERS). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567973">TAPE_SET_MEDIA_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567975">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567953">TapeMiniSetMediaParameters</a>
 

 

