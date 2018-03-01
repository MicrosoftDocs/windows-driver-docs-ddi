---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_VOLUME
title: IOCTL_CDROM_GET_VOLUME
author: windows-driver-content
description: Determines the current volume for each of its device's audio ports. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_get_volume.htm
old-project: storage
ms.assetid: 9ca03060-2f2b-4427-a161-fcce2be94b26
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_CDROM_GET_VOLUME, IOCTL_CDROM_GET_VOLUME control code [Storage Devices], k307_40300286-1334-4229-a798-2bfef8866ca7.xml, ntddcdrm/IOCTL_CDROM_GET_VOLUME, storage.ioctl_cdrom_get_volume
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: Obsolete, beginning with Windows Vista.
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
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_GET_VOLUME
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_VOLUME IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Determines the current volume for each of its device's audio ports.  Obsolete, beginning with Windows Vista.




## -ioctlparameters




### -input-buffer

Input buffer.


### -input-buffer-length

<i>
       Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location indicates the size, in bytes, of the buffer, which must be greater than or equal to <b> sizeof</b>(VOLUME_CONTROL).


### -output-buffer

The driver returns the <a href="..\ntddcdrm\ns-ntddcdrm-_volume_control.md">VOLUME_CONTROL</a> data in the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>.


### -output-buffer-length

Length of the <a href="..\ntddcdrm\ns-ntddcdrm-_volume_control.md">VOLUME_CONTROL</a> data.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(VOLUME_CONTROL) when the <b>Status</b> field is set to STATUS_SUCCESS. Otherwise, the <b>Information</b> field is set to zero, and the <b>Status</b> field possibly can be set to STATUS_BUFFER_TOO_SMALL, STATUS_DEVICE_NOT_READY, STATUS_IO_DEVICE_ERROR, STATUS_VERIFY_REQUIRED, or STATUS_IO_TIMEOUT.


## -remarks



Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.




## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_volume_control.md">VOLUME_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_GET_VOLUME control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

