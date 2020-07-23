---
UID: NI:ntddtape.IOCTL_TAPE_GET_POSITION
title: IOCTL_TAPE_GET_POSITION (ntddtape.h)
description: Returns the current absolute, logical, or pseudological partition and offset position on the tape.
old-location: storage\ioctl_tape_get_position.htm
tech.root: storage
ms.assetid: 358c3089-7238-4604-add8-575b611b3bc9
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_GET_POSITION IOCTL"]
ms.keywords: IOCTL_TAPE_GET_POSITION, IOCTL_TAPE_GET_POSITION control, IOCTL_TAPE_GET_POSITION control code [Storage Devices], k307_88069692-1167-4a21-914b-505e1100f6dc.xml, ntddtape/IOCTL_TAPE_GET_POSITION, storage.ioctl_tape_get_position
f1_keywords:
 - "ntddtape/IOCTL_TAPE_GET_POSITION"
 - "IOCTL_TAPE_GET_POSITION"
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
- IOCTL_TAPE_GET_POSITION
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_GET_POSITION IOCTL


## -description



Returns the current absolute, logical, or pseudological partition and offset position on the tape.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_get_position">TAPE_GET_POSITION</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_GET_POSITION).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_get_position">TAPE_GET_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetPosition</a>
 

 

