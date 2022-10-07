---
UID: NE:ntddstor._STORAGE_PORT_CODE_SET
tech.root: storage
title: STORAGE_PORT_CODE_SET
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the STORAGE_PORT_CODE_SET enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_PORT_CODE_SET
 - PSTORAGE_PORT_CODE_SET
 - STORAGE_PORT_CODE_SET
f1_keywords:
 - _STORAGE_PORT_CODE_SET
 - ntddstor/_STORAGE_PORT_CODE_SET
 - PSTORAGE_PORT_CODE_SET
 - ntddstor/PSTORAGE_PORT_CODE_SET
 - STORAGE_PORT_CODE_SET
 - ntddstor/STORAGE_PORT_CODE_SET
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_PORT_CODE_SET
---

## -description

Reserved for system use.

## -enum-fields

### -field StoragePortCodeSetReserved

Indicates an unknown storage adapter driver type.

### -field StoragePortCodeSetStorport

Storage adapter driver is a Storport-miniport driver.

### -field StoragePortCodeSetSCSIport

Storage adapter driver is a SCSI Port-miniport driver.

### -field StoragePortCodeSetSpaceport

Storage adapter driver is the Spaceport driver.

### -field StoragePortCodeSetATAport

xxStorage adapter driver is an ATA-port miniport driver.xxx

### -field StoragePortCodeSetUSBport

Storage adapter driver is the USB-storage port driver.

### -field StoragePortCodeSetSBP2port

Storage adapter driver is the SBP2 port driver.

### -field StoragePortCodeSetSDport

Storage adapter driver is an SD-port miniport driver.

## -see-also

[**STORAGE\_MINIPORT\_DESCRIPTOR**](ns-ntddstor-_storage_miniport_descriptor.md)
