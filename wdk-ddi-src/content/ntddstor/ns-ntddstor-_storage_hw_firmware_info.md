---
UID: NS:ntddstor._STORAGE_HW_FIRMWARE_INFO
title: _STORAGE_HW_FIRMWARE_INFO (ntddstor.h)
description: This structure contains information about the device firmware.
old-location: storage\storage_hw_firmware_info.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STORAGE_HW_FIRMWARE_INFO structure"]
ms.keywords: "*PSTORAGE_HW_FIRMWARE_INFO, PSTORAGE_HW_FIRMWARE_INFO, PSTORAGE_HW_FIRMWARE_INFO structure pointer [Storage Devices], STORAGE_HW_FIRMWARE_INFO, STORAGE_HW_FIRMWARE_INFO structure [Storage Devices], _STORAGE_HW_FIRMWARE_INFO, ntddstor/PSTORAGE_HW_FIRMWARE_INFO, ntddstor/STORAGE_HW_FIRMWARE_INFO, storage.storage_hw_firmware_info"
req.header: ntddstor.h
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
req.typenames: STORAGE_HW_FIRMWARE_INFO, *PSTORAGE_HW_FIRMWARE_INFO
f1_keywords:
 - _STORAGE_HW_FIRMWARE_INFO
 - ntddstor/_STORAGE_HW_FIRMWARE_INFO
 - PSTORAGE_HW_FIRMWARE_INFO
 - ntddstor/PSTORAGE_HW_FIRMWARE_INFO
 - STORAGE_HW_FIRMWARE_INFO
 - ntddstor/STORAGE_HW_FIRMWARE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_HW_FIRMWARE_INFO
---

# _STORAGE_HW_FIRMWARE_INFO structure


## -description

This structure contains information about the device firmware.

## -struct-fields

### -field Version

The version of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_INFO)

### -field Size

The size of this structure as a buffer including slot.

### -field SupportUpgrade

Indicates that this firmware supports an upgrade.

### -field Reserved0

Reserved for future use.

### -field SlotCount

The number of firmware slots on the device. This is the dimension of the Slot array.

<div class="alert"><b>Note</b>   Some devices can store more than 1 firmware image, if they have more than 1 firmware slot.</div>
<div> </div>

### -field ActiveSlot

The firmware slot containing the currently active/running firmware image.

### -field PendingActivateSlot

The firmware slot that is pending activation.

### -field FirmwareShared

Indicates that the firmware applies to both the device and controller/adapter, e.g. NVMe SSD.

### -field Reserved

Reserved for future use.

### -field ImagePayloadAlignment

The alignment of the image payload, in number of bytes. The maximum is PAGE_SIZE. The transfer size is a mutliple of this size. Some protocols require at least sector size. When this value is set to 0, this means that this value is invalid.

### -field ImagePayloadMaxSize

The image payload maximum size, this is used for a single command.

### -field Slot

Contains the slot information for each slot on the device.

