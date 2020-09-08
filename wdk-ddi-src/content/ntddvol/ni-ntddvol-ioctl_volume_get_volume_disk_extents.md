---
UID: NI:ntddvol.IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
title: IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS (ntddvol.h)
description: Returns the physical location(s) of a volume on one or more disks.
old-location: storage\ioctl_volume_get_volume_disk_extents.htm
tech.root: storage
ms.assetid: d831ea36-16ee-4723-95b1-f9903106b7c0
ms.date: 03/29/2018
keywords: ["IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS IOCTL"]
ms.keywords: IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS, IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS control, IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS control code [Storage Devices], k307_8f02f744-6892-4e3f-9b23-158370e6a1e9.xml, ntddvol/IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS, storage.ioctl_volume_get_volume_disk_extents
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows 2000 for volumes on fixed disks, but not for volumes on removable media. Available for use with removable media in Microsoft Windows 2000 SP4 and Windows XP SP1.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
 - ntddvol/IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvol.h
api_name:
 - IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS
---

# IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS IOCTL


## -description

Returns the physical location(s) of a volume on one or more disks. Extents are initially stored in the order in which they are created, but remirroring, splitting, or breaking a mirror, or actions taken during disaster recovery, can affect the order of disk extents.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns a VOLUME_DISK_EXTENTS structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>, which must be at least <b>sizeof</b>(VOLUME_DISK_EXTENTS).

### -output-buffer-length

The length of a VOLUME_DISK_EXTENTS structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The driver sets <b>Irp->IoStatus.Information</b> and the <b>Status</b> field as follows:

<ul>
<li>
If the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> is < <b>sizeof</b>(VOLUME_DISK_EXTENTS), the driver sets <b>Irp->IoStatus.Information</b> to zero and returns STATUS_INVALID_PARAMETER.

</li>
<li>
If the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> is at least <b>sizeof</b>(VOLUME_DISK_EXTENTS) but too small for all data to be returned, the driver sets <b>Irp->IoStatus.Information</b> to <b>sizeof</b>(VOLUME_DISK_EXTENTS) and sets <b>Status</b> to STATUS_BUFFER_OVERFLOW.

</li>
<li>
If the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> is large enough for all data to be returned, the driver sets <b>Irp->IoStatus.Information</b> to <b>sizeof</b>(VOLUME_DISK_EXTENTS) + ((NumberOfDiskExtents - 1) * <b>sizeof</b>(DISK_EXTENT)) and sets <b>Status</b> to STATUS_SUCCESS. 

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_disk_extent">DISK_EXTENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_disk_extents">VOLUME_DISK_EXTENTS</a>

