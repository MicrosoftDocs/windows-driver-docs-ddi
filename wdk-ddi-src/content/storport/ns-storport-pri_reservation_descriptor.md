---
UID: NS:storport.PRI_RESERVATION_DESCRIPTOR
title: PRI_RESERVATION_DESCRIPTOR
author: windows-driver-content
description: The PRI_RESERVATION_DESCRIPTOR structure is used to construct the PRI_RESERVATION_LIST structure that is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS.
old-location: storage\pri_reservation_descriptor.htm
old-project: storage
ms.assetid: f03506f6-404e-4635-a9ad-f2f36164ff2f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PPRI_RESERVATION_DESCRIPTOR, PPRI_RESERVATION_DESCRIPTOR, PPRI_RESERVATION_DESCRIPTOR structure pointer [Storage Devices], PRI_RESERVATION_DESCRIPTOR, PRI_RESERVATION_DESCRIPTOR structure [Storage Devices], storage.pri_reservation_descriptor, storport/PPRI_RESERVATION_DESCRIPTOR, storport/PRI_RESERVATION_DESCRIPTOR, structs-general_96e112cc-0cf3-442d-bb3a-7bcad8a95220.xml"
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
-	PRI_RESERVATION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: PRI_RESERVATION_DESCRIPTOR, *PPRI_RESERVATION_DESCRIPTOR
req.product: Windows 10 or later.
---

# PRI_RESERVATION_DESCRIPTOR structure


## -description


The PRI_RESERVATION_DESCRIPTOR structure is used to construct the <a href="..\storport\ns-storport-pri_reservation_list.md">PRI_RESERVATION_LIST</a> structure that is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS.


## -syntax


````
typedef struct {
  UCHAR ReservationKey[8];
  UCHAR ScopeSpecificAddress[4];
  UCHAR Reserved;
  UCHAR Type  :4;
  UCHAR Scope  :4;
  UCHAR Obsolete[2];
} PRI_RESERVATION_DESCRIPTOR, *PPRI_RESERVATION_DESCRIPTOR;
````


## -struct-fields




### -field ReservationKey

The reservation key under which the persistent reservation is held.


### -field ScopeSpecificAddress

The ScopeSpecificAddress field contains the element address, that has zeros placed in the most significant bits to fit the field.


### -field Reserved

Reserved. Must be zero.


### -field Type

The type of the persistent reservation as present in the Persistent Reserve Out command that created the persistent reservation.


### -field Scope

The scope of the persistent reservation as present in the Persistent Reserve Out command that created the persistent reservation.


### -field Obsolete

Reserved. Must be zero.


## -remarks



The <a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a> request is used to obtain information about persistent reservations and reservation keys that are active within a device server.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a>



<a href="..\storport\ns-storport-pri_reservation_list.md">PRI_RESERVATION_LIST</a>



 

 


