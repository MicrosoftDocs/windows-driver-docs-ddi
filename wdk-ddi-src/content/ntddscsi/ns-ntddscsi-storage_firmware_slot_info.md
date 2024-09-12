---
UID: NS:ntddscsi._STORAGE_FIRMWARE_SLOT_INFO
tech.root: storage
title: STORAGE_FIRMWARE_SLOT_INFO
ms.date: 06/24/2024
targetos: Windows
description: Learn about the STORAGE_FIRMWARE_SLOT_INFO structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddscsi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: STORAGE_FIRMWARE_SLOT_INFO, *PSTORAGE_FIRMWARE_SLOT_INFO
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _STORAGE_FIRMWARE_SLOT_INFO
 - PSTORAGE_FIRMWARE_SLOT_INFO
 - STORAGE_FIRMWARE_SLOT_INFO
f1_keywords:
 - _STORAGE_FIRMWARE_SLOT_INFO
 - ntddscsi/_STORAGE_FIRMWARE_SLOT_INFO
 - PSTORAGE_FIRMWARE_SLOT_INFO
 - ntddscsi/PSTORAGE_FIRMWARE_SLOT_INFO
 - STORAGE_FIRMWARE_SLOT_INFO
 - ntddscsi/STORAGE_FIRMWARE_SLOT_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_FIRMWARE_SLOT_INFO
---

## -description

The **STORAGE_FIRMWARE_SLOT_INFO** structure contains information about a firmware slot on a storage device.

## -struct-fields

### -field SlotNumber

The slot number of the firmware slot.

### -field ReadOnly

Boolean value that indicates whether the firmware slot is read-only. A value of TRUE indicates that the firmware slot is read-only.

### -field Reserved[6]

Reserved for system use.

### -field Revision

Union that contains the firmware revision information.

### -field Revision.Info[8]

Array of eight unsigned characters that contain the firmware revision information in a byte-by-byte format. It can be used to store or read the revision data as an array of bytes.

### -field Revision.AsUlonglong

Unsigned long long integer that represents the firmware revision information as a 64-bit value. It provides a way to access or store the revision information as a single large integer rather than as an array of bytes.

## -remarks

## -see-also
