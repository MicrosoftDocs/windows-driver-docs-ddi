---
UID: NI:ntddtape.IOCTL_TAPE_SET_POSITION
title: IOCTL_TAPE_SET_POSITION (ntddtape.h)
description: Moves the current position on the tape to the specified partition and offset, according to the given method.
old-location: storage\ioctl_tape_set_position.htm
tech.root: storage
ms.assetid: 93918e09-2742-47ca-94a5-043af2a3a338
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_SET_POSITION IOCTL"]
ms.keywords: IOCTL_TAPE_SET_POSITION, IOCTL_TAPE_SET_POSITION control, IOCTL_TAPE_SET_POSITION control code [Storage Devices], k307_3fc298fe-1a00-4bb5-8a10-09b5fec325b3.xml, ntddtape/IOCTL_TAPE_SET_POSITION, storage.ioctl_tape_set_position
f1_keywords:
 - "ntddtape/IOCTL_TAPE_SET_POSITION"
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddtape.h
api_name:
- IOCTL_TAPE_SET_POSITION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_SET_POSITION IOCTL


## -description



Moves the current position on the tape to the specified partition and offset, according to the given method.




## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_SET_POSITION). 

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_set_position">TAPE_SET_POSITION</a> structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> indicates the partition and offset to which the tape is to be moved. 

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_SET_POSITION). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_set_position">TAPE_SET_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetPosition</a>
 

 

