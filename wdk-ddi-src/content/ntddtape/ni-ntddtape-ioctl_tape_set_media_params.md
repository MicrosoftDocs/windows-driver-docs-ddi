---
UID: NI:ntddtape.IOCTL_TAPE_SET_MEDIA_PARAMS
title: IOCTL_TAPE_SET_MEDIA_PARAMS
author: windows-driver-content
description: Resets the block size of the media in the drive.
old-location: storage\ioctl_tape_set_media_params.htm
old-project: storage
ms.assetid: c1411e72-84b4-4021-bed6-17308415be3a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _TAPE_DRIVE_PROBLEM_TYPE, TAPE_DRIVE_PROBLEM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_TAPE_SET_MEDIA_PARAMS
req.alt-loc: Ntddtape.h
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
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_SET_MEDIA_PARAMS IOCTL



## -description

Resets the block size of the media in the drive.



Resets the block size of the media in the drive.



## -ioctlparameters

### -input-buffer

       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddtape\ns-ntddtape-_tape_set_media_parameters.md">TAPE_SET_MEDIA_PARAMETERS</a> structure containing the block size to be set. 


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_SET_MEDIA_PARAMETERS). 


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddtape\ns-ntddtape-_tape_set_media_parameters.md">TAPE_SET_MEDIA_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567953">TapeMiniSetMediaParameters</a>
</dt>
<dt>
<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_SET_MEDIA_PARAMS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

