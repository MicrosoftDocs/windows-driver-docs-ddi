---
UID: NS:ntddstor._STORAGE_HW_FIRMWARE_SLOT_INFO
title: "_STORAGE_HW_FIRMWARE_SLOT_INFO"
author: windows-driver-content
description: This structure contains information about a slot on a device.
old-location: storage\storage_hw_firmware_slot_info.htm
old-project: storage
ms.assetid: D5DF9785-83E0-4137-8E5F-357F94721CAD
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/STORAGE_HW_FIRMWARE_SLOT_INFO, STORAGE_HW_FIRMWARE_SLOT_INFO, PSTORAGE_HW_FIRMWARE_SLOT_INFO structure pointer [Storage Devices], _STORAGE_HW_FIRMWARE_SLOT_INFO, STORAGE_HW_FIRMWARE_SLOT_INFO structure [Storage Devices], *PSTORAGE_HW_FIRMWARE_SLOT_INFO, ntddstor/PSTORAGE_HW_FIRMWARE_SLOT_INFO, storage.storage_hw_firmware_slot_info, PSTORAGE_HW_FIRMWARE_SLOT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_HW_FIRMWARE_SLOT_INFO
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_HW_FIRMWARE_SLOT_INFO, STORAGE_HW_FIRMWARE_SLOT_INFO"
---

# _STORAGE_HW_FIRMWARE_SLOT_INFO structure


## -description


This structure contains information about a slot on a device.


## -syntax


````
typedef struct _STORAGE_HW_FIRMWARE_SLOT_INFO {
  ULONG Version;
  ULONG Size;
  UCHAR SlotNumber;
  UCHAR ReadOnly  :1;
  UCHAR Reserved0  :7;
  UCHAR Reserved1[6];
  UCHAR Revision[STORAGE_HW_FIRMWARE_REVISION_LENGTH];
} STORAGE_HW_FIRMWARE_SLOT_INFO, *PSTORAGE_HW_FIRMWARE_SLOT_INFO;
````


## -struct-fields




### -field Version

The version of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_SLOT_INFO)


### -field Size

The size of this structure.


### -field SlotNumber

The slot number of this slot.


### -field ReadOnly

Indicates whether this slot is read-only or not.


### -field Reserved0

Reserved for future use.


### -field Reserved1

Reserved for future use.


### -field Revision

The revision of the firmware on this slot.

