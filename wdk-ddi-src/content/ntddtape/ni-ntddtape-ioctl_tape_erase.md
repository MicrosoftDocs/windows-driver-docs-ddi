---
UID: NI:ntddtape.IOCTL_TAPE_ERASE
title: IOCTL_TAPE_ERASE (ntddtape.h)
description: Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a &#0034;secure&#0034;) operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a &#0034;quick&#0034;) operation that writes an end-of-recorded-data mark at the current position.
old-location: storage\ioctl_tape_erase.htm
tech.root: storage
ms.assetid: 75ec5c40-1ac2-472a-9923-26018eb6267c
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_ERASE IOCTL"]
ms.keywords: IOCTL_TAPE_ERASE, IOCTL_TAPE_ERASE control, IOCTL_TAPE_ERASE control code [Storage Devices], k307_cdbe0ea5-0d23-4ab0-9d37-2832d2367b81.xml, ntddtape/IOCTL_TAPE_ERASE, storage.ioctl_tape_erase
f1_keywords:
 - "ntddtape/IOCTL_TAPE_ERASE"
 - "IOCTL_TAPE_ERASE"
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
- IOCTL_TAPE_ERASE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_ERASE IOCTL


## -description



Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a "secure") operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a "quick") operation that writes an end-of-recorded-data mark at the current position.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_erase">TAPE_ERASE</a>. 

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_ERASE). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_erase">TAPE_ERASE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniErase</a>
 

 

