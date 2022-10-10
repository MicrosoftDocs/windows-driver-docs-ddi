---
UID: NS:sffdisk._SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
tech.root: sd
title: SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
ms.date: 10/06/2022
targetos: Windows
description: Learn more about the SFFDISK_QUERY_DEVICE_PROTOCOL_DATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: sffdisk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SFFDISK_QUERY_DEVICE_PROTOCOL_DATA, *PSFFDISK_QUERY_DEVICE_PROTOCOL_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sffdisk.h
api_name:
 - _SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - PSFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
f1_keywords:
 - _SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - sffdisk/_SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - PSFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - sffdisk/PSFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
 - sffdisk/SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - _SFFDISK_QUERY_DEVICE_PROTOCOL_DATA
---

## -description

The SFFDISK\_QUERY\_DEVICE\_PROTOCOL\_DATA structure is used in conjunction with the [**IOCTL\_SFFDISK\_QUERY\_DEVICE\_PROTOCOL**](ni-sffdisk-ioctl_sffdisk_query_device_protocol.md) request to report protocol data.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Reserved

Reserved.

### -field ProtocolGUID

On output, this member contains a GUID that uniquely identifies the protocol.

## -see-also

[**IOCTL\_SFFDISK\_QUERY\_DEVICE\_PROTOCOL**](ni-sffdisk-ioctl_sffdisk_query_device_protocol.md)
