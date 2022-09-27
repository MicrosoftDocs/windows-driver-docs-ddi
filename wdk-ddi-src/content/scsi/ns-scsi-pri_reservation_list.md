---
UID: NS:scsi.__unnamed_struct_11
title: PRI_RESERVATION_LIST (scsi.h)
description: The PRI_RESERVATION_LIST structure (scsi.h) contains a list of persistent reservations that are active within a device server.
tech.root: storage
ms.date: 09/19/2022
keywords: ["PRI_RESERVATION_LIST structure"]
ms.keywords: "*PPRI_RESERVATION_LIST, PPRI_RESERVATION_LIST, PPRI_RESERVATION_LIST structure pointer [Storage Devices], PRI_RESERVATION_LIST, PRI_RESERVATION_LIST structure [Storage Devices], storage.pri_reservation_list, storport/PPRI_RESERVATION_LIST, storport/PRI_RESERVATION_LIST, structs-general_10a53f53-2aed-4be1-bf2b-d61efa2c846f.xml"
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
targetos: Windows
req.typenames: PRI_RESERVATION_LIST, *PPRI_RESERVATION_LIST
f1_keywords:
 - PPRI_RESERVATION_LIST
 - scsi/PPRI_RESERVATION_LIST
 - PRI_RESERVATION_LIST
 - scsi/PRI_RESERVATION_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - PPRI_RESERVATION_LIST
 - PRI_RESERVATION_LIST
---

## -description

The **PRI_RESERVATION_LIST** structure is returned in response to a Persistent Reserve In command with ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS.

## -struct-fields

### -field Generation

The Generation field contains a 32-bit counter that is maintained by the device server, which is incremented every time a Persistent Reserve Out command requests a REGISTER, REGISTER AND IGNORE EXISTING KEY, CLEAR, PREEMPT, or PREEMPT AND ABORT service action.

### -field AdditionalLength

The AdditionalLength field contains a count of the number of bytes in the reservation descriptors.

### -field Reservations

An array of reservation descriptors.

## -remarks

The [**IOCTL_STORAGE_PERSISTENT_RESERVE_IN**](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_in) request is used to obtain information about persistent reservations and reservation keys that are active within a device server.

## -see-also

[**IOCTL_STORAGE_PERSISTENT_RESERVE_IN**](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_in)
