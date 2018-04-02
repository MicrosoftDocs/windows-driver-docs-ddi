---
UID: NS:scsi.PRI_REGISTRATION_LIST
title: PRI_REGISTRATION_LIST
author: windows-driver-content
description: The PRI_REGISTRATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_KEYS.
old-location: storage\pri_registration_list.htm
old-project: storage
ms.assetid: 47b1a263-f630-4348-893c-388cac4e511d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PPRI_REGISTRATION_LIST, PPRI_REGISTRATION_LIST, PPRI_REGISTRATION_LIST structure pointer [Storage Devices], PRI_REGISTRATION_LIST, PRI_REGISTRATION_LIST structure [Storage Devices], storage.pri_registration_list, storport/PPRI_REGISTRATION_LIST, storport/PRI_REGISTRATION_LIST, structs-general_ad5a83a3-3ac6-4579-be4f-c24181e9d59e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
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
-	PRI_REGISTRATION_LIST
product:
- Windows
targetos: Windows
req.typenames: PRI_REGISTRATION_LIST, *PPRI_REGISTRATION_LIST
req.product: Windows 10 or later.
---

# PRI_REGISTRATION_LIST structure


## -description


The PRI_REGISTRATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_KEYS.


## -struct-fields




### -field Generation

The Generation field contains a 32-bit counter that is maintained by the device server, which is incremented every time a Persistent Reserve Out command requests a REGISTER, REGISTER AND IGNORE

EXISTING KEY, CLEAR, PREEMPT, or PREEMPT AND ABORT service action.


### -field AdditionalLength

The AdditionalLength field contains a count of the number of bytes in the reservation key list.


### -field ReservationKeyList

 




#### - ReservationKeyList[0]

The reservation key list contains the 8-byte reservation keys for all initiators that have registered by using all ports with the device server.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560582">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a> request is used to obtain information about persistent reservations and reservation keys that are active within a device server.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560582">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a>
 

 

