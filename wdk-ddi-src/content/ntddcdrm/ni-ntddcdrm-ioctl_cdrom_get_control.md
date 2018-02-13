---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_CONTROL
title: IOCTL_CDROM_GET_CONTROL
author: windows-driver-content
description: This IOCTL request is obsolete. Do not use.Determines the current audio playback mode.
old-location: storage\ioctl_cdrom_get_control.htm
old-project: storage
ms.assetid: 3d474eb7-6622-48fd-bf40-c17d03933828
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_cdrom_get_control, IOCTL_CDROM_GET_CONTROL control code [Storage Devices], IOCTL_CDROM_GET_CONTROL, ntddcdrm/IOCTL_CDROM_GET_CONTROL, k307_441b4747-9431-42c3-b550-39aaea1229f1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_GET_CONTROL
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_CONTROL IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



This IOCTL request is obsolete. Do not use.

Determines the current audio playback mode. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_audio_control.md">CDROM_AUDIO_CONTROL</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(CDROM_AUDIO_CONTROL).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_DEVICE_NOT_READY, STATUS_IO_DEVICE_ERROR, STATUS_IO_TIMEOUT, STATUS_INSUFFICIENT_RESOURCES, STATUS_VERIFY_REQUIRED, or STATUS_INVALID_DEVICE_REQUEST.


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_audio_control.md">CDROM_AUDIO_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_GET_CONTROL control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

