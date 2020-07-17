---
UID: NE:ntddstor._STORAGE_PROTOCOL_TYPE
title: _STORAGE_PROTOCOL_TYPE (ntddstor.h)
description: This enumeration is used to define the different storage command protocols that are used between software and hardware.
old-location: storage\storage_protocol_type.htm
tech.root: storage
ms.assetid: 3CC4DF0A-26F1-4825-AD89-D56B0D5F4AC6
ms.date: 03/29/2018
keywords: ["_STORAGE_PROTOCOL_TYPE enumeration"]
ms.keywords: "*PSTORAGE_PROTOCOL_TYPE, ProtocolTypeAta, ProtocolTypeMaxReserved, ProtocolTypeNvme, ProtocolTypeProprietary, ProtocolTypeScsi, ProtocolTypeSd, ProtocolTypeUfs, ProtocolTypeUnknown, STORAGE_PROTOCOL_TYPE, STORAGE_PROTOCOL_TYPE enumeration [Storage Devices], _STORAGE_PROTOCOL_TYPE, ntddstor/ProtocolTypeAta, ntddstor/ProtocolTypeMaxReserved, ntddstor/ProtocolTypeNvme, ntddstor/ProtocolTypeProprietary, ntddstor/ProtocolTypeScsi, ntddstor/ProtocolTypeSd, ntddstor/ProtocolTypeUfs, ntddstor/ProtocolTypeUnknown, ntddstor/STORAGE_PROTOCOL_TYPE, storage.storage_protocol_type"
f1_keywords:
 - "ntddstor/STORAGE_PROTOCOL_TYPE"
 - "STORAGE_PROTOCOL_TYPE"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- STORAGE_PROTOCOL_TYPE
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PROTOCOL_TYPE, *PSTORAGE_PROTOCOL_TYPE
---

# _STORAGE_PROTOCOL_TYPE enumeration


## -description


This enumeration is used to define the different storage command protocols that are used between software and hardware.


## -enum-fields




### -field ProtocolTypeUnknown

Unknown protocol type.


### -field ProtocolTypeScsi

SCSI protocol type.


### -field ProtocolTypeAta

ATA protocol type.


### -field ProtocolTypeNvme

NVMe protocol type.


### -field ProtocolTypeSd

SD protocol type.


### -field ProtocolTypeUfs

UFS protocol type.


### -field ProtocolTypeProprietary

 Vendor-specific protocol type.


### -field ProtocolTypeMaxReserved

Reserved.


## -remarks



Protocol types that are 128 (0x80) and above in value are reserved for Microsoft use.



