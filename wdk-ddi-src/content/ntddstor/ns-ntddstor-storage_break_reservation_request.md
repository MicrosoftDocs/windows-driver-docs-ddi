---
UID: NS:ntddstor.STORAGE_BREAK_RESERVATION_REQUEST
title: STORAGE_BREAK_RESERVATION_REQUEST
author: windows-driver-content
description: The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the IOCTL_STORAGE_BREAK_RESERVATION request to free a disk resource that was previously reserved.
old-location: storage\storage_break_reservation_request.htm
old-project: storage
ms.assetid: 06de4432-9437-4275-8d1e-606f209e1468
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.storage_break_reservation_request, structs-general_f902ea12-3b3d-4eb7-9ac2-9a5abfabe13c.xml, STORAGE_BREAK_RESERVATION_REQUEST, STORAGE_BREAK_RESERVATION_REQUEST structure [Storage Devices], *PSTORAGE_BREAK_RESERVATION_REQUEST, PSTORAGE_BREAK_RESERVATION_REQUEST structure pointer [Storage Devices], ntddstor/STORAGE_BREAK_RESERVATION_REQUEST, ntddstor/PSTORAGE_BREAK_RESERVATION_REQUEST, PSTORAGE_BREAK_RESERVATION_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	ntddstor.h
apiname: 
-	STORAGE_BREAK_RESERVATION_REQUEST
product: Windows
targetos: Windows
req.typenames: STORAGE_BREAK_RESERVATION_REQUEST, *PSTORAGE_BREAK_RESERVATION_REQUEST
---

# STORAGE_BREAK_RESERVATION_REQUEST structure


## -description


The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_break_reservation.md">IOCTL_STORAGE_BREAK_RESERVATION</a> request to free a disk resource that was previously reserved. 


## -syntax


````
typedef struct STORAGE_BREAK_RESERVATION_REQUEST {
  ULONG Length;
  UCHAR _unused;
  UCHAR PathId;
  UCHAR TargetId;
  UCHAR Lun;
} STORAGE_BREAK_RESERVATION_REQUEST, *PSTORAGE_BREAK_RESERVATION_REQUEST;
````


## -struct-fields




### -field Length

Contains the length of this structure in bytes.


### -field _unused

Reserved. Do not use. 


### -field PathId

Indicates the number of the bus to be reset. 


### -field TargetId

Contains the number of the target device.


### -field Lun

Contains the logical unit number. 


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_break_reservation.md">IOCTL_STORAGE_BREAK_RESERVATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_BREAK_RESERVATION_REQUEST structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

