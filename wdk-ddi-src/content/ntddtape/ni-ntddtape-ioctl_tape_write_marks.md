---
UID: NI:ntddtape.IOCTL_TAPE_WRITE_MARKS
title: IOCTL_TAPE_WRITE_MARKS (ntddtape.h)
description: Writes one of setmarks, filemarks, short filemarks, or long filemarks to tape.
old-location: storage\ioctl_tape_write_marks.htm
tech.root: storage
ms.assetid: cc4dabe3-4e14-4495-89b4-37f1a31ea62d
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_WRITE_MARKS IOCTL"]
ms.keywords: IOCTL_TAPE_WRITE_MARKS, IOCTL_TAPE_WRITE_MARKS control, IOCTL_TAPE_WRITE_MARKS control code [Storage Devices], k307_f1ba7d65-28cf-4a26-b385-462ca5018d88.xml, ntddtape/IOCTL_TAPE_WRITE_MARKS, storage.ioctl_tape_write_marks
f1_keywords:
 - "ntddtape/IOCTL_TAPE_WRITE_MARKS"
 - "IOCTL_TAPE_WRITE_MARKS"
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
- IOCTL_TAPE_WRITE_MARKS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_WRITE_MARKS IOCTL


## -description



Writes one of setmarks, filemarks, short filemarks, or long filemarks to tape.




## -ioctlparameters




### -input-buffer

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_write_marks">TAPE_WRITE_MARKS</a> structure in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> indicates the type and number of marks to write. 

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_WRITE_MARKS). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes written. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_MEDIA_WRITE_PROTECTED, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_write_marks">TAPE_WRITE_MARKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWriteMarks</a>
 

 

