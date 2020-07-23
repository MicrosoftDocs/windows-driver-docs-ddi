---
UID: NI:ntddtape.IOCTL_TAPE_GET_STATUS
title: IOCTL_TAPE_GET_STATUS (ntddtape.h)
description: Returns the current status of the drive in the Status field of the I/O status block.
old-location: storage\ioctl_tape_get_status.htm
tech.root: storage
ms.assetid: d5e491b8-d40c-4f2c-9117-5c3cb71913f7
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_GET_STATUS IOCTL"]
ms.keywords: IOCTL_TAPE_GET_STATUS, IOCTL_TAPE_GET_STATUS control, IOCTL_TAPE_GET_STATUS control code [Storage Devices], k307_8ab90364-adac-4937-9036-aa28ddeffb19.xml, ntddtape/IOCTL_TAPE_GET_STATUS, storage.ioctl_tape_get_status
f1_keywords:
 - "ntddtape/IOCTL_TAPE_GET_STATUS"
 - "IOCTL_TAPE_GET_STATUS"
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
- IOCTL_TAPE_GET_STATUS
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_GET_STATUS IOCTL


## -description



Returns the current status of the drive in the <b>Status</b> field of the I/O status block. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to one of the following NT status values: 

<ul>
<li>
STATUS_SUCCESS

</li>
<li>
STATUS_INSUFFICIENT_RESOURCES

</li>
<li>
STATUS_NOT_IMPLEMENTED

</li>
<li>
STATUS_INVALID_DEVICE_REQUEST

</li>
<li>
STATUS_INVALID_PARAMETER

</li>
<li>
STATUS_VERIFY_REQUIRED

</li>
<li>
STATUS_BUS_RESET

</li>
<li>
STATUS_SETMARK_DETECTED

</li>
<li>
STATUS_FILEMARK_DETECTED

</li>
<li>
STATUS_BEGINNING_OF_MEDIA

</li>
<li>
STATUS_END_OF_MEDIA

</li>
<li>
STATUS_BUFFER_OVERFLOW

</li>
<li>
STATUS_NO_DATA_DETECTED

</li>
<li>
STATUS_EOM_OVERFLOW

</li>
<li>
STATUS_NO_MEDIA

</li>
<li>
STATUS_IO_DEVICE_ERROR

</li>
<li>
STATUS_UNRECOGNIZED_MEDIA

</li>
<li>
STATUS_DEVICE_NOT_READY

</li>
<li>
STATUS_MEDIA_WRITE_PROTECTED

</li>
<li>
STATUS_DEVICE_DATA_ERROR

</li>
<li>
STATUS_NO_SUCH_DEVICE

</li>
<li>
STATUS_INVALID_BLOCK_LENGTH

</li>
<li>
STATUS_IO_TIMEOUT

</li>
<li>
STATUS_DEVICE_NOT_CONNECTED

</li>
<li>
STATUS_DATA_OVERRUN

</li>
<li>
STATUS_DEVICE_BUSY

</li>
<li>
STATUS_DEVICE_REQUIRES_CLEANING

</li>
<li>
STATUS_CLEANER_CARTRIDGE_INSTALLED

</li>
</ul>
Each of these NT status values correspond to a value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a> enumerator. For more information about the significance of these values and a mapping between the NT status values and the TAPE_STATUS values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/processing-tape-device-control-requests">Processing Tape Device Control Requests</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>
 

 

