---
UID: NI:ntddvol.IOCTL_VOLUME_READ_PLEX
title: IOCTL_VOLUME_READ_PLEX (ntddvol.h)
description: Performs a read on a specific plex of a volume.
old-location: storage\ioctl_volume_read_plex.htm
tech.root: storage
ms.assetid: 187e15d2-b527-4dab-81ea-498663363f8b
ms.date: 03/29/2018
keywords: ["IOCTL_VOLUME_READ_PLEX IOCTL"]
ms.keywords: IOCTL_VOLUME_READ_PLEX, IOCTL_VOLUME_READ_PLEX control, IOCTL_VOLUME_READ_PLEX control code [Storage Devices], k307_9f88e325-8c32-4be3-acaa-5df77ee023c2.xml, ntddvol/IOCTL_VOLUME_READ_PLEX, storage.ioctl_volume_read_plex
f1_keywords:
 - "ntddvol/IOCTL_VOLUME_READ_PLEX"
 - "IOCTL_VOLUME_READ_PLEX"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddvol.h
api_name:
- IOCTL_VOLUME_READ_PLEX
targetos: Windows
req.typenames: 
---

# IOCTL_VOLUME_READ_PLEX IOCTL


## -description



Performs a read on a specific <a href="https://docs.microsoft.com/windows-hardware/drivers/">plex</a> of a volume. Because all plexes are identical, the volume manager can retrieve data from any of a volume's plexes during a normal read operation. The volume manager spreads reads among a volume's plexes, to balance the I/O load on the physical media and to maximize read performance. 

If, however, an application or kernel-mode component must read data from a particular plex instead of letting the volume manager pick one, it can use this IOCTL to do so. 




## -ioctlparameters




### -input-buffer

Caller inserts the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_read_plex_input">VOLUME_READ_PLEX_INPUT</a> structure, containing the logical offset, at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to the value of <b>sizeof</b>(VOLUME_READ_PLEX_INPUT).


### -output-buffer

Like <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>, this IOCTL stores the read data in the memory buffer passed as a memory descriptor list (MDL) in the <b>Irp->MdlAddress</b> field. 


### -output-buffer-length

The length of the buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the operation is successful, the volume manager sets the <b>Status</b> field to STATUS_SUCCESS.

The VOLUME_READ_PLEX_INPUT structure at <b>Irp->AssociatedIrp.SystemBuffer</b> has a <b>Length</b> member that must be aligned on a 512-byte boundary. If <b>Length</b> does not have the proper alignment, the operation fails and the volume manager sets the <b>Status</b> field to VKE_EINVAL. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_read_plex_input">VOLUME_READ_PLEX_INPUT</a>
 

 

