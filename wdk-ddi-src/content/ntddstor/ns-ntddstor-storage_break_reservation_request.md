---
UID: NS:ntddstor.STORAGE_BREAK_RESERVATION_REQUEST
title: STORAGE_BREAK_RESERVATION_REQUEST
author: windows-driver-content
description: The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the IOCTL_STORAGE_BREAK_RESERVATION request to free a disk resource that was previously reserved.
old-location: storage\storage_break_reservation_request.htm
tech.root: storage
ms.assetid: 06de4432-9437-4275-8d1e-606f209e1468
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_BREAK_RESERVATION_REQUEST, PSTORAGE_BREAK_RESERVATION_REQUEST, PSTORAGE_BREAK_RESERVATION_REQUEST structure pointer [Storage Devices], STORAGE_BREAK_RESERVATION_REQUEST, STORAGE_BREAK_RESERVATION_REQUEST structure [Storage Devices], ntddstor/PSTORAGE_BREAK_RESERVATION_REQUEST, ntddstor/STORAGE_BREAK_RESERVATION_REQUEST, storage.storage_break_reservation_request, structs-general_f902ea12-3b3d-4eb7-9ac2-9a5abfabe13c.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	STORAGE_BREAK_RESERVATION_REQUEST
product:
- Windows
targetos: Windows
req.typenames: STORAGE_BREAK_RESERVATION_REQUEST, *PSTORAGE_BREAK_RESERVATION_REQUEST
---

# STORAGE_BREAK_RESERVATION_REQUEST structure


## -description


The STORAGE_BREAK_RESERVATION_REQUEST structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560533">IOCTL_STORAGE_BREAK_RESERVATION</a> request to free a disk resource that was previously reserved. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560533">IOCTL_STORAGE_BREAK_RESERVATION</a>
 

 

