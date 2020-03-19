---
UID: NS:ntddcdvd._AACS_SERIAL_NUMBER
title: _AACS_SERIAL_NUMBER (ntddcdvd.h)
description: The AACS_SERIAL_NUMBER structure contains an Advanced Access Content System (AACS) serial number and corresponding message authentication code (MAC).
old-location: storage\aacs_serial_number.htm
tech.root: storage
ms.assetid: 1436c8a5-9160-41d8-acc1-0af6acadfdba
ms.date: 03/29/2018
keywords: ["_AACS_SERIAL_NUMBER structure"]
ms.keywords: "*PAACS_SERIAL_NUMBER, AACS_SERIAL_NUMBER, AACS_SERIAL_NUMBER structure [Storage Devices], PAACS_SERIAL_NUMBER, PAACS_SERIAL_NUMBER structure pointer [Storage Devices], _AACS_SERIAL_NUMBER, ntddcdvd/AACS_SERIAL_NUMBER, ntddcdvd/PAACS_SERIAL_NUMBER, storage.aacs_serial_number, structs-DVD_baba43db-de96-4f55-9d26-46cc56dce390.xml"
f1_keywords:
 - "ntddcdvd/AACS_SERIAL_NUMBER"
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
- ntddcdvd.h
api_name:
- AACS_SERIAL_NUMBER
product:
- Windows
targetos: Windows
req.typenames: AACS_SERIAL_NUMBER, *PAACS_SERIAL_NUMBER
---

# _AACS_SERIAL_NUMBER structure


## -description


The AACS_SERIAL_NUMBER structure contains an Advanced Access Content System (AACS) serial number and corresponding message authentication code (MAC).


## -struct-fields




### -field PrerecordedSerialNumber

The serial number.


### -field MAC

The message authentication code (MAC) that the client uses to verify that the serial number is for the current AACS authentication sequence.


## -remarks



Clients retrieve the AACS serial number with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_serial_number">IOCTL_AACS_READ_SERIAL_NUMBER</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_serial_number">IOCTL_AACS_READ_SERIAL_NUMBER</a>
 

 

