---
UID: NS:scsi.PRI_FULL_STATUS_LIST_HEADER
tech.root: storage
title: PRI_FULL_STATUS_LIST_HEADER (scsi.h)
ms.date: 03/20/2024
targetos: Windows
description: The PRI_FULL_STATUS_LIST_HEADER structure is the first member of a PRI_FULL_STATUS_LIST that is returned in response to a Persistent Reserve In command with ServiceAction=RESERVATION_ACTION_READ_FULL_STATUS.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: scsi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PRI_FULL_STATUS_LIST_HEADER, *PPRI_FULL_STATUS_LIST_HEADER
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PRI_FULL_STATUS_LIST_HEADER
 - PPRI_FULL_STATUS_LIST_HEADER
f1_keywords:
 - PRI_FULL_STATUS_LIST_HEADER
 - scsi/PRI_FULL_STATUS_LIST_HEADER
 - PPRI_FULL_STATUS_LIST_HEADER
 - scsi/PPRI_FULL_STATUS_LIST_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - PRI_FULL_STATUS_LIST_HEADER
---

## -description

The **PRI_FULL_STATUS_LIST_HEADER** structure is the first member of a **[PRI_FULL_STATUS_LIST](ns-scsi-pri_full_status_list.md)** that is returned in response to a Persistent Reserve In command with `ServiceAction=RESERVATION_ACTION_READ_FULL_STATUS`.

## -struct-fields

### -field Generation[4]

The Generation field contains a 32-bit counter that is maintained by the device server, which is incremented every time a Persistent Reserve In command requests a RESERVATION_ACTION_READ_FULL_STATUS service action.

### -field AdditionalLength[4]

The *AdditionalDescriptorLength* field indicates the number of bytes that follow.

## -remarks

## -see-also

- **[PRI_FULL_STATUS_LIST](ns-scsi-pri_full_status_list.md)**
