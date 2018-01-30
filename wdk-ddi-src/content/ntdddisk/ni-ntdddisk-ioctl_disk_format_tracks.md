---
UID: NI:ntdddisk.IOCTL_DISK_FORMAT_TRACKS
title: IOCTL_DISK_FORMAT_TRACKS
author: windows-driver-content
description: Formats the specified set of contiguous tracks on the disk.
old-location: storage\ioctl_disk_format_tracks.htm
old-project: storage
ms.assetid: f27f962f-badc-4e6f-ad3b-ce2a0c8ce825
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_disk_format_tracks, IOCTL_DISK_FORMAT_TRACKS control code [Storage Devices], IOCTL_DISK_FORMAT_TRACKS, ntdddisk/IOCTL_DISK_FORMAT_TRACKS, k307_c50ddad4-851d-474e-92c1-13520556173b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	Ntdddisk.h
apiname:
-	IOCTL_DISK_FORMAT_TRACKS
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_FORMAT_TRACKS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Formats the specified set of contiguous tracks on the disk.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_format_parameters.md">FORMAT_PARAMETERS</a> data. <b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -output-buffer

The device driver returns an array of BAD_TRACK_NUMBER values to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

Length of the buffer.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the size of the returned bad-track array when the <b>Status</b> field is set to STATUS_SUCCESS. Otherwise, the <b>Information</b> field is zero and the <b>Status</b> field possibly can be set to STATUS_INVALID_PARAMETER or STATUS_MEDIA_WRITE_PROTECTED if the media is removable.


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_format_parameters.md">FORMAT_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_FORMAT_TRACKS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

