---
UID: NS:storport.PRI_RESERVATION_LIST
title: PRI_RESERVATION_LIST
author: windows-driver-content
description: The PRI_RESERVATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS.
old-location: storage\pri_reservation_list.htm
old-project: storage
ms.assetid: 5756e907-008a-49c3-b1cd-947cb0ce1bd4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PPRI_RESERVATION_LIST, PPRI_RESERVATION_LIST, PPRI_RESERVATION_LIST structure pointer [Storage Devices], PRI_RESERVATION_LIST, PRI_RESERVATION_LIST structure [Storage Devices], storage.pri_reservation_list, storport/PPRI_RESERVATION_LIST, storport/PRI_RESERVATION_LIST, structs-general_10a53f53-2aed-4be1-bf2b-d61efa2c846f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Ntddstor.h, Minitape.h, Scsi.h
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
-	storport.h
api_name:
-	PRI_RESERVATION_LIST
product: Windows
targetos: Windows
req.typenames: PRI_RESERVATION_LIST, *PPRI_RESERVATION_LIST
req.product: Windows 10 or later.
---

# PRI_RESERVATION_LIST structure


## -description


The PRI_RESERVATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS.


## -syntax


````
typedef struct {
  UCHAR                      Generation[4];
  UCHAR                      AdditionalLength[4];
  PRI_RESERVATION_DESCRIPTOR Reservations[];
} PRI_RESERVATION_LIST, *PPRI_RESERVATION_LIST;
````


## -struct-fields




### -field Generation

The Generation field contains a 32-bit counter that is maintained by the device server, which is incremented every time a Persistent Reserve Out command requests a REGISTER, REGISTER AND IGNORE

EXISTING KEY, CLEAR, PREEMPT, or PREEMPT AND ABORT service action.


### -field AdditionalLength

The AdditionalLength field contains a count of the number of bytes in the reservation descriptors.


### -field Reservations

An array of reservation descriptors.


## -remarks



The <a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a> request is used to obtain information about persistent reservations and reservation keys that are active within a device server.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a>



 

 


