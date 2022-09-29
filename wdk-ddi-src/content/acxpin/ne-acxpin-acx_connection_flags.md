---
UID: NE:acxpin._ACX_CONNECTION_FLAGS
tech.root: audio
title: ACX_CONNECTION_FLAGS
ms.date: 03/25/2022
targetos: Windows
description: The ACX_CONNECTION_FLAGS enumeration is used by the ACX_CONNECTION structure to specify the ACX object identifier types.
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
 - _ACX_CONNECTION_FLAGS
 - ACX_CONNECTION_FLAGS
f1_keywords:
 - _ACX_CONNECTION_FLAGS
 - acxpin/_ACX_CONNECTION_FLAGS
 - ACX_CONNECTION_FLAGS
 - acxpin/ACX_CONNECTION_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_CONNECTION_FLAGS** enumeration is used by the [ACX_CONNECTION](ns-acxpin-acx_connection.md) structure to specify the ACX object identifier types.

## -enum-fields

### -field AcxConnectionNoFlags

Indicates that there are no flags set.

### -field AcxConnectionFromPinId

Indicates that the connection is *from* a pin ID.

### -field AcxConnectionFromPinObject

Indicates that the connection is *from* an object.

### -field AcxConnectionToPinId

Indicates that the connection is *to* a pin ID.

### -field AcxConnectionToPinObject

Indicates that the connection is *to* a pin object.

### -field AcxConnectionValidFlags

For internal validation, do not use.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header](index.md)


