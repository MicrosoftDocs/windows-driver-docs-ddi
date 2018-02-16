---
UID: NI:ntddvol.IOCTL_VOLUME_READ_PLEX
title: IOCTL_VOLUME_READ_PLEX
author: windows-driver-content
description: Performs a read on a specific plex of a volume.
old-location: storage\ioctl_volume_read_plex.htm
old-project: storage
ms.assetid: 187e15d2-b527-4dab-81ea-498663363f8b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_volume_read_plex, IOCTL_VOLUME_READ_PLEX control code [Storage Devices], IOCTL_VOLUME_READ_PLEX, ntddvol/IOCTL_VOLUME_READ_PLEX, k307_9f88e325-8c32-4be3-acaa-5df77ee023c2.xml
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
-	Ntddvol.h
apiname:
-	IOCTL_VOLUME_READ_PLEX
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS"
---

# IOCTL_VOLUME_READ_PLEX IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Performs a read on a specific <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">plex</a> of a volume. Because all plexes are identical, the volume manager can retrieve data from any of a volume's plexes during a normal read operation. The volume manager spreads reads among a volume's plexes, to balance the I/O load on the physical media and to maximize read performance. 

If, however, an application or kernel-mode component must read data from a particular plex instead of letting the volume manager pick one, it can use this IOCTL to do so. 




## -ioctlparameters




### -input-buffer

Caller inserts the <a href="..\ntddvol\ns-ntddvol-_volume_read_plex_input.md">VOLUME_READ_PLEX_INPUT</a> structure, containing the logical offset, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to the value of <b>sizeof</b>(VOLUME_READ_PLEX_INPUT).


### -output-buffer

Like <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>, this IOCTL stores the read data in the memory buffer passed as a memory descriptor list (MDL) in the <b>Irp-&gt;MdlAddress</b> field. 


### -output-buffer-length

The length of the buffer.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the operation is successful, the volume manager sets the <b>Status</b> field to STATUS_SUCCESS.

The VOLUME_READ_PLEX_INPUT structure at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> has a <b>Length</b> member that must be aligned on a 512-byte boundary. If <b>Length</b> does not have the proper alignment, the operation fails and the volume manager sets the <b>Status</b> field to VKE_EINVAL. 


## -see-also

<a href="..\ntddvol\ns-ntddvol-_volume_read_plex_input.md">VOLUME_READ_PLEX_INPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_VOLUME_READ_PLEX control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

