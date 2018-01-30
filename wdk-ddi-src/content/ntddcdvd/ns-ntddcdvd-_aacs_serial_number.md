---
UID: NS:ntddcdvd._AACS_SERIAL_NUMBER
title: "_AACS_SERIAL_NUMBER"
author: windows-driver-content
description: The AACS_SERIAL_NUMBER structure contains an Advanced Access Content System (AACS) serial number and corresponding message authentication code (MAC).
old-location: storage\aacs_serial_number.htm
old-project: storage
ms.assetid: 1436c8a5-9160-41d8-acc1-0af6acadfdba
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PAACS_SERIAL_NUMBER, ntddcdvd/AACS_SERIAL_NUMBER, structs-DVD_baba43db-de96-4f55-9d26-46cc56dce390.xml, AACS_SERIAL_NUMBER structure [Storage Devices], PAACS_SERIAL_NUMBER, _AACS_SERIAL_NUMBER, AACS_SERIAL_NUMBER, PAACS_SERIAL_NUMBER structure pointer [Storage Devices], ntddcdvd/PAACS_SERIAL_NUMBER, storage.aacs_serial_number"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdvd.h
apiname:
-	AACS_SERIAL_NUMBER
product: Windows
targetos: Windows
req.typenames: "*PAACS_SERIAL_NUMBER, AACS_SERIAL_NUMBER"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_SERIAL_NUMBER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

