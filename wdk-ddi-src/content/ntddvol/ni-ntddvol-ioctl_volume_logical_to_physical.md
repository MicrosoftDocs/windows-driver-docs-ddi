---
UID: NI:ntddvol.IOCTL_VOLUME_LOGICAL_TO_PHYSICAL
title: IOCTL_VOLUME_LOGICAL_TO_PHYSICAL
author: windows-driver-content
description: Returns physical offsets and physical disk numbers for a given volume logical offset.
old-location: storage\ioctl_volume_logical_to_physical.htm
old-project: storage
ms.assetid: deadee81-4a6d-4c8b-80fd-46c29becc2cf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _VIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VOLUME_LOGICAL_TO_PHYSICAL
req.alt-loc: Ntddvol.h
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
req.typenames: VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
---

# IOCTL_VOLUME_LOGICAL_TO_PHYSICAL IOCTL



## -description

Returns physical offsets and physical disk numbers for a given volume logical offset. 

For example, a logical volume offset inside a mirrored volume with two <a href="wdkgloss.p#wdkgloss.plex#wdkgloss.plex"><i>plex</i></a> corresponds to two physical offsets, one in each of the two disks participating in the mirror. In response to this IOCTL, the volume manager returns two physical offsets and two physical disk numbers for the logical volume offset. 

The volume manager supports this IOCTL for all types of basic and dynamic volumes.



Returns physical offsets and physical disk numbers for a given volume logical offset. 

For example, a logical volume offset inside a mirrored volume with two <a href="wdkgloss.p#wdkgloss.plex#wdkgloss.plex"><i>plex</i></a> corresponds to two physical offsets, one in each of the two disks participating in the mirror. In response to this IOCTL, the volume manager returns two physical offsets and two physical disk numbers for the logical volume offset. 

The volume manager supports this IOCTL for all types of basic and dynamic volumes.



## -ioctlparameters

### -input-buffer
Caller inserts the <a href="..\ntddvol\ns-ntddvol-_volume_logical_offset.md">VOLUME_LOGICAL_OFFSET</a> structure containing the logical offset at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to the value of <b>sizeof</b>(VOLUME_LOGICAL_OFFSET).


### -output-buffer
The output buffer size must be large enough to hold the structure <a href="..\ntddvol\ns-ntddvol-_volume_physical_offsets.md">VOLUME_PHYSICAL_OFFSETS</a>, which contains a variable-length array of structures of type <a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>. 

The volume manager returns one or more physical offsets and disk numbers in the VOLUME_PHYSICAL_OFFSETS structure at the beginning of the buffer, at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation is successful, the <b>Status</b> member is set to STATUS_SUCCESS. Otherwise, the <b>Status</b> member is set to the appropriate error code. Possible error codes include the following: 



The input buffer is too small. 



The output buffer is too small. The volume manager sets the <b>Irp-&gt;IoStatus.Information</b> member to the size of the output buffer the caller should have provided. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddvol\ni-ntddvol-ioctl_volume_physical_to_logical.md">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>
</dt>
<dt>
<a href="..\ntddvol\ns-ntddvol-_volume_logical_offset.md">VOLUME_LOGICAL_OFFSET</a>
</dt>
<dt>
<a href="..\ntddvol\ns-ntddvol-_volume_physical_offsets.md">VOLUME_PHYSICAL_OFFSETS</a>
</dt>
<dt>
<a href="..\ntddvol\ns-ntddvol-_volume_physical_offset.md">VOLUME_PHYSICAL_OFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_VOLUME_LOGICAL_TO_PHYSICAL control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

