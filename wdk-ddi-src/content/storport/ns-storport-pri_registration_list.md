---
UID: NS:storport.PRI_REGISTRATION_LIST
title: PRI_REGISTRATION_LIST
author: windows-driver-content
description: The PRI_REGISTRATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_KEYS.
old-location: storage\pri_registration_list.htm
old-project: storage
ms.assetid: 47b1a263-f630-4348-893c-388cac4e511d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPRI_REGISTRATION_LIST, PPRI_REGISTRATION_LIST, PPRI_REGISTRATION_LIST structure pointer [Storage Devices], PRI_REGISTRATION_LIST, PRI_REGISTRATION_LIST structure [Storage Devices], storage.pri_registration_list, storport/PPRI_REGISTRATION_LIST, storport/PRI_REGISTRATION_LIST, structs-general_ad5a83a3-3ac6-4579-be4f-c24181e9d59e.xml"
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
-	PRI_REGISTRATION_LIST
product: Windows
targetos: Windows
req.typenames: PRI_REGISTRATION_LIST, *PPRI_REGISTRATION_LIST
req.product: Windows 10 or later.
---

# PRI_REGISTRATION_LIST structure


## -description


The PRI_REGISTRATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_KEYS.


## -syntax


````
typedef struct {
  UCHAR Generation[4];
  UCHAR AdditionalLength[4];
  UCHAR ReservationKeyList[0][8];
} PRI_REGISTRATION_LIST, *PPRI_REGISTRATION_LIST;
````


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



The <a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a> request is used to obtain information about persistent reservations and reservation keys that are active within a device server.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PRI_REGISTRATION_LIST structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

