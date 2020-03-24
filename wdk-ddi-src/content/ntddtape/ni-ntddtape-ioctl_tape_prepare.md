---
UID: NI:ntddtape.IOCTL_TAPE_PREPARE
title: IOCTL_TAPE_PREPARE (ntddtape.h)
description: Loads or unloads the tape, resets tape tension, locks or unlocks the ejection mechanism, or formats the tape.
old-location: storage\ioctl_tape_prepare.htm
tech.root: storage
ms.assetid: 0e016f3a-4f3a-4256-bb7b-10a5f955b930
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_PREPARE IOCTL"]
ms.keywords: IOCTL_TAPE_PREPARE, IOCTL_TAPE_PREPARE control, IOCTL_TAPE_PREPARE control code [Storage Devices], k307_a564f3c9-909a-437c-973c-0e6c25fad061.xml, ntddtape/IOCTL_TAPE_PREPARE, storage.ioctl_tape_prepare
f1_keywords:
 - "ntddtape/IOCTL_TAPE_PREPARE"
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
- IOCTL_TAPE_PREPARE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_PREPARE IOCTL


## -description



Loads or unloads the tape, resets tape tension, locks or unlocks the ejection mechanism, or formats the tape.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_prepare">TAPE_PREPARE</a> structure that indicates the type of operation.

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_PREPARE). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_INSUFFICIENT_RESOURCES, STATUS_DEVICE_NOT_CONNECTED, STATUS_MEDIA_WRITE_PROTECTED, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_prepare">TAPE_PREPARE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniPrepare</a>
 

 

