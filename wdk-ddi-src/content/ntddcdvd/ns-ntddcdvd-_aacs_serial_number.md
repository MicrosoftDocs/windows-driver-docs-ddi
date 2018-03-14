---
UID: NS:ntddcdvd._AACS_SERIAL_NUMBER
title: "_AACS_SERIAL_NUMBER"
author: windows-driver-content
description: The AACS_SERIAL_NUMBER structure contains an Advanced Access Content System (AACS) serial number and corresponding message authentication code (MAC).
old-location: storage\aacs_serial_number.htm
old-project: storage
ms.assetid: 1436c8a5-9160-41d8-acc1-0af6acadfdba
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PAACS_SERIAL_NUMBER, AACS_SERIAL_NUMBER, AACS_SERIAL_NUMBER structure [Storage Devices], PAACS_SERIAL_NUMBER, PAACS_SERIAL_NUMBER structure pointer [Storage Devices], _AACS_SERIAL_NUMBER, ntddcdvd/AACS_SERIAL_NUMBER, ntddcdvd/PAACS_SERIAL_NUMBER, storage.aacs_serial_number, structs-DVD_baba43db-de96-4f55-9d26-46cc56dce390.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdvd.h
api_name:
-	AACS_SERIAL_NUMBER
product: Windows
targetos: Windows
req.typenames: AACS_SERIAL_NUMBER, *PAACS_SERIAL_NUMBER
---

# _AACS_SERIAL_NUMBER structure


## -description


The AACS_SERIAL_NUMBER structure contains an Advanced Access Content System (AACS) serial number and corresponding message authentication code (MAC).


## -syntax


````
typedef struct _AACS_SERIAL_NUMBER {
  UCHAR PrerecordedSerialNumber[16];
  UCHAR MAC[16];
} AACS_SERIAL_NUMBER, *PAACS_SERIAL_NUMBER;
````


## -struct-fields




### -field PrerecordedSerialNumber

The serial number.


### -field MAC

The message authentication code (MAC) that the client uses to verify that the serial number is for the current AACS authentication sequence.


## -remarks



Clients retrieve the AACS serial number with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_serial_number.md">IOCTL_AACS_READ_SERIAL_NUMBER</a> request.




## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_serial_number.md">IOCTL_AACS_READ_SERIAL_NUMBER</a>



 

 


