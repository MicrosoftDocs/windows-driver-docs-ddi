---
UID: NI:ntddcdrm.IOCTL_CDROM_SET_VOLUME
title: IOCTL_CDROM_SET_VOLUME
author: windows-driver-content
description: Resets the volume for its device's audio ports. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_set_volume.htm
old-project: storage
ms.assetid: 9331ad0b-42e0-4f20-9410-fb135f4791b0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_cdrom_set_volume, IOCTL_CDROM_SET_VOLUME control code [Storage Devices], IOCTL_CDROM_SET_VOLUME, ntddcdrm/IOCTL_CDROM_SET_VOLUME, k307_d31efcd3-1072-49db-82d0-6ecce05a8964.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntddcdrm.h
apiname: 
-	IOCTL_CDROM_SET_VOLUME
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_SET_VOLUME IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Resets the volume for its device's audio ports.  Obsolete, beginning with Windows Vista.




## -ioctlparameters




### -input-buffer

The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains the <a href="..\ntddcdrm\ns-ntddcdrm-_volume_control.md">VOLUME_CONTROL</a> value or values to be set. 


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> in the I/O stack location indicates the size, in bytes, of the buffer, which must be greater than or equal to  <b>sizeof</b>(VOLUME_CONTROL).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_DEVICE_NOT_READY, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_VERIFY_REQUIRED, or STATUS_INVALID_DEVICE_REQUEST.


## -remarks


Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.



## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_volume_control.md">VOLUME_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_SET_VOLUME control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

