---
UID: NE:minitape._TAPE_STATUS
title: _TAPE_STATUS
author: windows-driver-content
description: The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device.
old-location: storage\tape_status.htm
old-project: storage
ms.assetid: 45e85ad1-5b75-410e-b9dd-061051bbaa74
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _TAPE_STATUS, TAPE_STATUS, *PTAPE_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: minitape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAPE_STATUS
req.alt-loc: minitape.h
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
req.typenames: TAPE_STATUS, *PTAPE_STATUS
---

# _TAPE_STATUS enumeration



## -description
The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device.



## -syntax

````
typedef enum _TAPE_STATUS { 
  TAPE_STATUS_SEND_SRB_AND_CALLBACK        = 0,
  TAPE_STATUS_CALLBACK                     = 1,
  TAPE_STATUS_CHECK_TEST_UNIT_READY        = 2,
  TAPE_STATUS_SUCCESS                      = 3,
  TAPE_STATUS_INSUFFICIENT_RESOURCES       = 4,
  TAPE_STATUS_NOT_IMPLEMENTED              = 5,
  TAPE_STATUS_INVALID_DEVICE_REQUEST       = 6,
  TAPE_STATUS_INVALID_PARAMETER            = 7,
  TAPE_STATUS_MEDIA_CHANGED                = 8,
  TAPE_STATUS_BUS_RESET                    = 9,
  TAPE_STATUS_SETMARK_DETECTED             = 10,
  TAPE_STATUS_FILEMARK_DETECTED            = 11,
  TAPE_STATUS_BEGINNING_OF_MEDIA           = 12,
  TAPE_STATUS_END_OF_MEDIA                 = 13,
  TAPE_STATUS_BUFFER_OVERFLOW              = 14,
  TAPE_STATUS_NO_DATA_DETECTED             = 15,
  TAPE_STATUS_EOM_OVERFLOW                 = 16,
  TAPE_STATUS_NO_MEDIA                     = 17,
  TAPE_STATUS_IO_DEVICE_ERROR              = 18,
  TAPE_STATUS_UNRECOGNIZED_MEDIA           = 19,
  TAPE_STATUS_DEVICE_NOT_READY             = 20,
  TAPE_STATUS_MEDIA_WRITE_PROTECTED        = 21,
  TAPE_STATUS_DEVICE_DATA_ERROR            = 22,
  TAPE_STATUS_NO_SUCH_DEVICE               = 23,
  TAPE_STATUS_INVALID_BLOCK_LENGTH         = 24,
  TAPE_STATUS_IO_TIMEOUT                   = 25,
  TAPE_STATUS_DEVICE_NOT_CONNECTED         = 26,
  TAPE_STATUS_DATA_OVERRUN                 = 27,
  TAPE_STATUS_DEVICE_BUSY                  = 28,
  TAPE_STATUS_REQUIRES_CLEANING            = 29,
  TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED  = 30
} TAPE_STATUS, *PTAPE_STATUS;
````


## -enum-fields

### -field TAPE_STATUS_SEND_SRB_AND_CALLBACK

Directs the tape class driver to send the SRB to the device. A tape miniclass routine usually returns this status after filling in the SRB passed by the tape class driver. If the operation is successful, the class driver increments a counter called a "call number" and calls the miniclass routine again. If the SRB fails, the class driver might call the miniclass routine again. For more information about how and when tape miniclass drivers should report this status value, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>. 


### -field TAPE_STATUS_CALLBACK

Directs the tape class driver to increment the call number counter without sending an SRB to the device. For more information about how tape miniclass drivers should make use of this status value, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>. 


### -field TAPE_STATUS_CHECK_TEST_UNIT_READY

Directs the tape class driver to create an SRB for the TEST UNIT READY command and to send the SRB to the device. 


### -field TAPE_STATUS_SUCCESS

Indicates that the operation was successful. 


### -field TAPE_STATUS_INSUFFICIENT_RESOURCES

Indicates that there were not enough resources available to the miniclass driver for it to complete the operation. 


### -field TAPE_STATUS_NOT_IMPLEMENTED

Indicates that the requested operation is not supported. 


### -field TAPE_STATUS_INVALID_DEVICE_REQUEST

Indicates that the requested operation is invalid. 


### -field TAPE_STATUS_INVALID_PARAMETER

Indicates that one or more of the parameter values provided with the request are invalid. 


### -field TAPE_STATUS_MEDIA_CHANGED

Indicates that the media in the drive might have changed. 


### -field TAPE_STATUS_BUS_RESET

Indicates that the bus has been reset. 


### -field TAPE_STATUS_SETMARK_DETECTED

Indicates that a setmark was encountered during a tape operation. 


### -field TAPE_STATUS_FILEMARK_DETECTED

Indicates that a filemark was encountered during a tape operation. 


### -field TAPE_STATUS_BEGINNING_OF_MEDIA

Indicates that the beginning of the media was encountered during a tape operation. 


### -field TAPE_STATUS_END_OF_MEDIA

Indicates that the end of the media was encountered during a tape operation. 


### -field TAPE_STATUS_BUFFER_OVERFLOW

Indicates that a buffer overflow occurred. 


### -field TAPE_STATUS_NO_DATA_DETECTED

Indicates that no data was detected. 


### -field TAPE_STATUS_EOM_OVERFLOW

Indicates that an attempt was made to exceed the physical end of the media during a tape operation. 


### -field TAPE_STATUS_NO_MEDIA

Indicates that the tape operation failed, because there is no media in the drive. 


### -field TAPE_STATUS_IO_DEVICE_ERROR

Indicates that an I/O error occurred during a tape operation. 


### -field TAPE_STATUS_UNRECOGNIZED_MEDIA

Indicates that the type of the media is not supported. 


### -field TAPE_STATUS_DEVICE_NOT_READY

Indicates that the device is not ready. 


### -field TAPE_STATUS_MEDIA_WRITE_PROTECTED

Indicates that the media is write protected. 


### -field TAPE_STATUS_DEVICE_DATA_ERROR

Indicates that a cyclic redundancy check (CRC) error occurred. 


### -field TAPE_STATUS_NO_SUCH_DEVICE

Indicates that no such device exists. 


### -field TAPE_STATUS_INVALID_BLOCK_LENGTH

Indicates that the block length is invalid. 


### -field TAPE_STATUS_IO_TIMEOUT

Indicates that the I/O operation timed out. 


### -field TAPE_STATUS_DEVICE_NOT_CONNECTED

Indicates that the device is disconnected. 


### -field TAPE_STATUS_DATA_OVERRUN

Indicates that the tape operation could not be performed because of a data overrun. 


### -field TAPE_STATUS_DEVICE_BUSY

Indicates that the tape operation could not be performed, because the device is busy. 


### -field TAPE_STATUS_REQUIRES_CLEANING

Indicates that the tape operation could not be performed because the device requires cleaning. 


### -field TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED

Indicates that the media currently in the drive is a cleaner cartridge. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_status.md">IOCTL_TAPE_GET_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_STATUS enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

