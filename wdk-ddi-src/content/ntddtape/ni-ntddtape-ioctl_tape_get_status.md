---
UID: NI:ntddtape.IOCTL_TAPE_GET_STATUS
title: IOCTL_TAPE_GET_STATUS
author: windows-driver-content
description: Returns the current status of the drive in the Status field of the I/O status block.
old-location: storage\ioctl_tape_get_status.htm
old-project: storage
ms.assetid: d5e491b8-d40c-4f2c-9117-5c3cb71913f7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _TAPE_DRIVE_PROBLEM_TYPE, TAPE_DRIVE_PROBLEM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_TAPE_GET_STATUS
req.alt-loc: Ntddtape.h
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
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_GET_STATUS IOCTL



## -description

Returns the current status of the drive in the <b>Status</b> field of the I/O status block. 



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

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to one of the following NT status values: 

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES

STATUS_NOT_IMPLEMENTED

STATUS_INVALID_DEVICE_REQUEST

STATUS_INVALID_PARAMETER

STATUS_VERIFY_REQUIRED

STATUS_BUS_RESET

STATUS_SETMARK_DETECTED

STATUS_FILEMARK_DETECTED

STATUS_BEGINNING_OF_MEDIA

STATUS_END_OF_MEDIA

STATUS_BUFFER_OVERFLOW

STATUS_NO_DATA_DETECTED

STATUS_EOM_OVERFLOW

STATUS_NO_MEDIA

STATUS_IO_DEVICE_ERROR

STATUS_UNRECOGNIZED_MEDIA

STATUS_DEVICE_NOT_READY

STATUS_MEDIA_WRITE_PROTECTED

STATUS_DEVICE_DATA_ERROR

STATUS_NO_SUCH_DEVICE

STATUS_INVALID_BLOCK_LENGTH

STATUS_IO_TIMEOUT

STATUS_DEVICE_NOT_CONNECTED

STATUS_DATA_OVERRUN

STATUS_DEVICE_BUSY

STATUS_DEVICE_REQUIRES_CLEANING

STATUS_CLEANER_CARTRIDGE_INSTALLED

Each of these NT status values correspond to a value in the <a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a> enumerator. For more information about the significance of these values and a mapping between the NT status values and the TAPE_STATUS values, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_GET_STATUS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

