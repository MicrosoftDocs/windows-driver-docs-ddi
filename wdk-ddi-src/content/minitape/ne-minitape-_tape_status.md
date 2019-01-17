---
UID: NE:minitape._TAPE_STATUS
title: "_TAPE_STATUS"
description: The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device.
old-location: storage\tape_status.htm
tech.root: storage
ms.assetid: 45e85ad1-5b75-410e-b9dd-061051bbaa74
ms.date: 03/29/2018
ms.keywords: "*PTAPE_STATUS, PTAPE_STATUS, PTAPE_STATUS enumeration pointer [Storage Devices], TAPE_STATUS, TAPE_STATUS enumeration [Storage Devices], TAPE_STATUS_BEGINNING_OF_MEDIA, TAPE_STATUS_BUFFER_OVERFLOW, TAPE_STATUS_BUS_RESET, TAPE_STATUS_CALLBACK, TAPE_STATUS_CHECK_TEST_UNIT_READY, TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED, TAPE_STATUS_DATA_OVERRUN, TAPE_STATUS_DEVICE_BUSY, TAPE_STATUS_DEVICE_DATA_ERROR, TAPE_STATUS_DEVICE_NOT_CONNECTED, TAPE_STATUS_DEVICE_NOT_READY, TAPE_STATUS_END_OF_MEDIA, TAPE_STATUS_EOM_OVERFLOW, TAPE_STATUS_FILEMARK_DETECTED, TAPE_STATUS_INSUFFICIENT_RESOURCES, TAPE_STATUS_INVALID_BLOCK_LENGTH, TAPE_STATUS_INVALID_DEVICE_REQUEST, TAPE_STATUS_INVALID_PARAMETER, TAPE_STATUS_IO_DEVICE_ERROR, TAPE_STATUS_IO_TIMEOUT, TAPE_STATUS_MEDIA_CHANGED, TAPE_STATUS_MEDIA_WRITE_PROTECTED, TAPE_STATUS_NOT_IMPLEMENTED, TAPE_STATUS_NO_DATA_DETECTED, TAPE_STATUS_NO_MEDIA, TAPE_STATUS_NO_SUCH_DEVICE, TAPE_STATUS_REQUIRES_CLEANING, TAPE_STATUS_SEND_SRB_AND_CALLBACK, TAPE_STATUS_SETMARK_DETECTED, TAPE_STATUS_SUCCESS, TAPE_STATUS_UNRECOGNIZED_MEDIA, _TAPE_STATUS, minitape/PTAPE_STATUS, minitape/TAPE_STATUS, minitape/TAPE_STATUS_BEGINNING_OF_MEDIA, minitape/TAPE_STATUS_BUFFER_OVERFLOW, minitape/TAPE_STATUS_BUS_RESET, minitape/TAPE_STATUS_CALLBACK, minitape/TAPE_STATUS_CHECK_TEST_UNIT_READY, minitape/TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED, minitape/TAPE_STATUS_DATA_OVERRUN, minitape/TAPE_STATUS_DEVICE_BUSY, minitape/TAPE_STATUS_DEVICE_DATA_ERROR, minitape/TAPE_STATUS_DEVICE_NOT_CONNECTED, minitape/TAPE_STATUS_DEVICE_NOT_READY, minitape/TAPE_STATUS_END_OF_MEDIA, minitape/TAPE_STATUS_EOM_OVERFLOW, minitape/TAPE_STATUS_FILEMARK_DETECTED, minitape/TAPE_STATUS_INSUFFICIENT_RESOURCES, minitape/TAPE_STATUS_INVALID_BLOCK_LENGTH, minitape/TAPE_STATUS_INVALID_DEVICE_REQUEST, minitape/TAPE_STATUS_INVALID_PARAMETER, minitape/TAPE_STATUS_IO_DEVICE_ERROR, minitape/TAPE_STATUS_IO_TIMEOUT, minitape/TAPE_STATUS_MEDIA_CHANGED, minitape/TAPE_STATUS_MEDIA_WRITE_PROTECTED, minitape/TAPE_STATUS_NOT_IMPLEMENTED, minitape/TAPE_STATUS_NO_DATA_DETECTED, minitape/TAPE_STATUS_NO_MEDIA, minitape/TAPE_STATUS_NO_SUCH_DEVICE, minitape/TAPE_STATUS_REQUIRES_CLEANING, minitape/TAPE_STATUS_SEND_SRB_AND_CALLBACK, minitape/TAPE_STATUS_SETMARK_DETECTED, minitape/TAPE_STATUS_SUCCESS, minitape/TAPE_STATUS_UNRECOGNIZED_MEDIA, storage.tape_status, structs-tape_c79a2dd4-8c91-4735-9440-de39b23aa982.xml"
ms.topic: enum
req.header: minitape.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	minitape.h
api_name:
-	TAPE_STATUS
product:
- Windows
targetos: Windows
req.typenames: TAPE_STATUS, *PTAPE_STATUS
---

# _TAPE_STATUS enumeration


## -description


The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device.


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


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560625">IOCTL_TAPE_GET_STATUS</a>
 

 

