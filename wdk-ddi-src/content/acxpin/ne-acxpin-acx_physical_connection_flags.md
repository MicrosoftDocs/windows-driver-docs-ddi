---
UID: NE:acxpin._ACX_PHYSICAL_CONNECTION_FLAGS
tech.root: audio
title: ACX_PHYSICAL_CONNECTION_FLAGS
ms.date: 12/15/2021
targetos: Windows
description: The ACX_PHYSICAL_CONNECTION_FLAGS enumeration is used by the ACX_PHYSICAL_CONNECTION structure to initialize a physical connection.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_PHYSICAL_CONNECTION_FLAGS
 - ACX_PHYSICAL_CONNECTION_FLAGS
f1_keywords:
 - _ACX_PHYSICAL_CONNECTION_FLAGS
 - acxpin/_ACX_PHYSICAL_CONNECTION_FLAGS
 - ACX_PHYSICAL_CONNECTION_FLAGS
 - acxpin/ACX_PHYSICAL_CONNECTION_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_PHYSICAL_CONNECTION_FLAGS** enumeration is used by the [ACX_PHYSICAL_CONNECTION](ns-acxpin-acx_physical_connection.md) structure to initialize a physical connection.

## -enum-fields

### -field AcxPhysicalConnectionNoFlags

Indicates that no flags are set.

### -field AcxPhysicalConnectionFromPinId

Indicates that the physical connection is from a PIN whose ID is specified.

### -field AcxPhysicalConnectionFromPinObject

Indicates that the physical connection is from a PIN which is represented by the specified PIN object.

### -field AcxPhysicalConnectionValidFlags

For internal validation, do not use.

## -remarks

## -see-also

- [ACX_PHYSICAL_CONNECTION](ns-acxpin-acx_physical_connection.md)

READY2GO