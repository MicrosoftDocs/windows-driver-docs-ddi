---
UID: NS:storport.PRI_RESERVATION_LIST
title: PRI_RESERVATION_LIST
author: windows-driver-content
description: The PRI_RESERVATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS.
old-location: storage\pri_reservation_list.htm
old-project: storage
ms.assetid: 5756e907-008a-49c3-b1cd-947cb0ce1bd4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PPRI_RESERVATION_LIST, ,, A, E, I, L, N, O, P, PPRI_RESERVATION_LIST, PPRI_RESERVATION_LIST structure pointer [Storage Devices], PRI_RESERVATION_LIST, PRI_RESERVATION_LIST structure [Storage Devices], R, S, T, V, _, storage.pri_reservation_list, storport/PPRI_RESERVATION_LIST, storport/PRI_RESERVATION_LIST, structs-general_10a53f53-2aed-4be1-bf2b-d61efa2c846f.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PRI_RESERVATION_LIST structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

