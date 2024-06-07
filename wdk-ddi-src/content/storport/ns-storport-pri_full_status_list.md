---
UID: NS:storport.PRI_FULL_STATUS_LIST
tech.root: storage
title: PRI_FULL_STATUS_LIST (storport.h)
ms.date: 03/22/2024
targetos: Windows
description: The PRI_FULL_STATUS_LIST structure is returned in response to a Persistent Reserve In command with ServiceAction=RESERVATION_ACTION_READ_FULL_STATUS.
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
req.typenames: PRI_FULL_STATUS_LIST, *PPRI_FULL_STATUS_LIST
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
 - PRI_FULL_STATUS_LIST
 - PPRI_FULL_STATUS_LIST
f1_keywords:
 - PRI_FULL_STATUS_LIST
 - storport/PRI_FULL_STATUS_LIST
 - PPRI_FULL_STATUS_LIST
 - storport/PPRI_FULL_STATUS_LIST
dev_langs:
 - c++
helpviewer_keywords:
 - PRI_FULL_STATUS_LIST
---

## -description

The **PRI_FULL_STATUS_LIST** structure is returned in response to a Persistent Reserve In command with `ServiceAction=RESERVATION_ACTION_READ_FULL_STATUS`.

## -struct-fields

### -field Generation[4]

The Generation field contains a 32-bit counter that is maintained by the device server, which is incremented every time a Persistent Reserve In command requests a RESERVATION_ACTION_READ_FULL_STATUS service action.

### -field AdditionalLength[4]

The *AdditionalDescriptorLength* field indicates the number of bytes in the full status list.

### -field FullStatusDescriptors[ANYSIZE_ARRAY]

An array of **[PRI_FULL_STATUS_DESCRIPTOR](ns-storport-pri_full_status_descriptor.md)** structures.

## -remarks

## -see-also

- **[PRI_FULL_STATUS_DESCRIPTOR](ns-storport-pri_full_status_descriptor.md)**
- **[PRI_FULL_STATUS_DESCRIPTOR_HEADER](ns-storport-pri_full_status_descriptor_header.md)**
