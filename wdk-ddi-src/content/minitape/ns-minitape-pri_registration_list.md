---
UID: NS:minitape.__unnamed_struct_9
title: PRI_REGISTRATION_LIST (minitape.h)
description: The PRI_REGISTRATION_LIST structure (minitape.h) contains information about persistent reservations and reservation keys that are active within a device server.
tech.root: storage
ms.date: 09/26/2022
keywords: ["PRI_REGISTRATION_LIST structure"]
ms.keywords: "*PPRI_REGISTRATION_LIST, PPRI_REGISTRATION_LIST, PPRI_REGISTRATION_LIST structure pointer [Storage Devices], PRI_REGISTRATION_LIST, PRI_REGISTRATION_LIST structure [Storage Devices], storage.pri_registration_list, storport/PPRI_REGISTRATION_LIST, storport/PRI_REGISTRATION_LIST, structs-general_ad5a83a3-3ac6-4579-be4f-c24181e9d59e.xml"
req.header: minitape.h
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
targetos: Windows
req.typenames: PRI_REGISTRATION_LIST, *PPRI_REGISTRATION_LIST
f1_keywords:
 - PPRI_REGISTRATION_LIST
 - minitape/PPRI_REGISTRATION_LIST
 - PRI_REGISTRATION_LIST
 - minitape/PRI_REGISTRATION_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - PPRI_REGISTRATION_LIST
 - PRI_REGISTRATION_LIST
---

## -description

The PRI_REGISTRATION_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_KEYS.

## -struct-fields

### -field Generation[4]

The Generation field contains a 32-bit counter that is maintained by the device server, which is incremented every time a Persistent Reserve Out command requests a REGISTER, REGISTER AND IGNORE EXISTING KEY, CLEAR, PREEMPT, or PREEMPT AND ABORT service action.

### -field AdditionalLength[4]

The AdditionalLength field contains a count of the number of bytes in the reservation key list.

### -field ReservationKeyList[0]

The reservation key list contains the 8-byte reservation keys for all initiators that have registered by using all ports with the device server.

## -remarks

The [IOCTL_STORAGE_PERSISTENT_RESERVE_IN](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_in) request is used to obtain information about persistent reservations and reservation keys that are active within a device server.

## -see-also

[IOCTL_STORAGE_PERSISTENT_RESERVE_IN](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_in)
