---
UID: NS:ntddstor._STORAGE_HW_FIRMWARE_ACTIVATE
title: STORAGE_HW_FIRMWARE_ACTIVATE (ntddstor.h)
description: Learn more about the STORAGE_HW_FIRMWARE_ACTIVATE structure.
tech.root: storage
ms.date: 03/29/2024
keywords: ["STORAGE_HW_FIRMWARE_ACTIVATE structure"]
req.header: ntddstor.h
req.construct-type: structure
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: STORAGE_HW_FIRMWARE_ACTIVATE, *PSTORAGE_HW_FIRMWARE_ACTIVATE
f1_keywords:
 - _STORAGE_HW_FIRMWARE_ACTIVATE
 - ntddstor/_STORAGE_HW_FIRMWARE_ACTIVATE
 - PSTORAGE_HW_FIRMWARE_ACTIVATE
 - ntddstor/PSTORAGE_HW_FIRMWARE_ACTIVATE
 - STORAGE_HW_FIRMWARE_ACTIVATE
 - ntddstor/STORAGE_HW_FIRMWARE_ACTIVATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_HW_FIRMWARE_ACTIVATE
 - PSTORAGE_HW_FIRMWARE_ACTIVATE
 - STORAGE_HW_FIRMWARE_ACTIVATE
---

# STORAGE_HW_FIRMWARE_ACTIVATE structure (ntddstor.h)



## -description

The **STORAGE_HW_FIRMWARE_ACTIVATE** structure contains information about the downloaded firmware to activate.

## -struct-fields

### -field Version

The version of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_ACTIVATE).

### -field Size

The size of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_ACTIVATE).

### -field Flags

The flags associated with the activation request. The following are valid flags that can be set in this member.

| Flag | Description |
| ---- | ----------- |
| STORAGE_HW_FIRMWARE_REQUEST_FLAG_CONTROLLER | Indicates that the target of the request is a controller or adapter, different than the device handle or object itself (e.g. NVMe SSD or HBA). |
| STORAGE_HW_FIRMWARE_REQUEST_FLAG_SWITCH_TO_EXISTING_FIRMWARE | Indicates that an existing firmware image in the specified slot should be activated. |
| STORAGE_HW_FIRMWARE_REQUEST_FLAG_REPLACE_EXISTING_IMAGE | Indicates that the existing firmware in the slot should be activated with a controller reset. Available starting with Windows 11, version 24H2. |

### -field Slot

The slot with the firmware image that is to be activated.

### -field Reserved0

Reserved for future use.
