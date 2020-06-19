---
UID: NI:ntddvol.IOCTL_VOLUME_LOGICAL_TO_PHYSICAL
title: IOCTL_VOLUME_LOGICAL_TO_PHYSICAL (ntddvol.h)
description: Returns physical offsets and physical disk numbers for a given volume logical offset.
old-location: storage\ioctl_volume_logical_to_physical.htm
tech.root: storage
ms.assetid: deadee81-4a6d-4c8b-80fd-46c29becc2cf
ms.date: 03/29/2018
keywords: ["IOCTL_VOLUME_LOGICAL_TO_PHYSICAL IOCTL"]
ms.keywords: IOCTL_VOLUME_LOGICAL_TO_PHYSICAL, IOCTL_VOLUME_LOGICAL_TO_PHYSICAL control, IOCTL_VOLUME_LOGICAL_TO_PHYSICAL control code [Storage Devices], k307_a96f1e34-902f-4d5f-8935-96a963cfa041.xml, ntddvol/IOCTL_VOLUME_LOGICAL_TO_PHYSICAL, storage.ioctl_volume_logical_to_physical
f1_keywords:
 - "ntddvol/IOCTL_VOLUME_LOGICAL_TO_PHYSICAL"
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
- IOCTL_VOLUME_LOGICAL_TO_PHYSICAL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VOLUME_LOGICAL_TO_PHYSICAL IOCTL


## -description



Returns physical offsets and physical disk numbers for a given volume logical offset. 

For example, a logical volume offset inside a mirrored volume with two <a href="https://docs.microsoft.com/windows-hardware/drivers/">plex</a> corresponds to two physical offsets, one in each of the two disks participating in the mirror. In response to this IOCTL, the volume manager returns two physical offsets and two physical disk numbers for the logical volume offset. 

The volume manager supports this IOCTL for all types of basic and dynamic volumes.




## -ioctlparameters




### -input-buffer

Caller inserts the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_logical_offset">VOLUME_LOGICAL_OFFSET</a> structure containing the logical offset at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to the value of <b>sizeof</b>(VOLUME_LOGICAL_OFFSET).


### -output-buffer

The output buffer size must be large enough to hold the structure <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_physical_offsets">VOLUME_PHYSICAL_OFFSETS</a>, which contains a variable-length array of structures of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_physical_offset">VOLUME_PHYSICAL_OFFSET</a>. 

The volume manager returns one or more physical offsets and disk numbers in the VOLUME_PHYSICAL_OFFSETS structure at the beginning of the buffer, at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the operation is successful, the <b>Status</b> member is set to STATUS_SUCCESS. Otherwise, the <b>Status</b> member is set to the appropriate error code. Possible error codes include the following: 






**STATUS_BUFFER_TOO_SMALL**

The output buffer is too small. The volume manager sets the <b>Irp->IoStatus.Information</b> member to the size of the output buffer the caller should have provided. 


**STATUS_INVALID_PARAMETER**

The input buffer is too small. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_physical_to_logical">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_logical_offset">VOLUME_LOGICAL_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_physical_offset">VOLUME_PHYSICAL_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_physical_offsets">VOLUME_PHYSICAL_OFFSETS</a>
 

 

