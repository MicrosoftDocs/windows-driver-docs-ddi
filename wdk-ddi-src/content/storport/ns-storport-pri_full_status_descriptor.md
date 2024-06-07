---
UID: NS:storport.PRI_FULL_STATUS_DESCRIPTOR
tech.root: storage
title: PRI_FULL_STATUS_DESCRIPTOR (storport.h)
ms.date: 03/22/2024
targetos: Windows
description: The PRI_FULL_STATUS_DESCRIPTOR structure is used to construct the PRI_FULL_STATUS_LIST structure that is returned in response to a Persistent Reserve In command.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PRI_FULL_STATUS_DESCRIPTOR, *PPRI_FULL_STATUS_DESCRIPTOR
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - PRI_FULL_STATUS_DESCRIPTOR
 - PPRI_FULL_STATUS_DESCRIPTOR
f1_keywords:
 - PRI_FULL_STATUS_DESCRIPTOR
 - storport/PRI_FULL_STATUS_DESCRIPTOR
 - PPRI_FULL_STATUS_DESCRIPTOR
 - storport/PPRI_FULL_STATUS_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - PRI_FULL_STATUS_DESCRIPTOR
---

## -description

The **PRI_FULL_STATUS_DESCRIPTOR** structure is used to construct the **[PRI_FULL_STATUS_LIST](ns-storport-pri_full_status_list.md)** structure that is returned in response to a Persistent Reserve In command with `ServiceAction=RESERVATION_ACTION_READ_FULL_STATUS`.

## -struct-fields

### -field Header

Contains the **[PRI_FULL_STATUS_DESCRIPTOR_HEADER](ns-storport-pri_full_status_descriptor_header.md)** structure.

### -field TransportID[ANYSIZE_ARRAY]

The *TransportID* identifies the initiator port that is described by this full status descriptor.

## -remarks

The **[IOCTL_STORAGE_PERSISTENT_RESERVE_IN](../ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_in.md)** request is used to obtain information about persistent reservations and reservation keys that are active within a device server.

## -see-also

- **[IOCTL_STORAGE_PERSISTENT_RESERVE_IN](../ntddstor/ni-ntddstor-ioctl_storage_persistent_reserve_in.md)**
- **[PRI_FULL_STATUS_DESCRIPTOR_HEADER](ns-storport-pri_full_status_descriptor_header.md)**
