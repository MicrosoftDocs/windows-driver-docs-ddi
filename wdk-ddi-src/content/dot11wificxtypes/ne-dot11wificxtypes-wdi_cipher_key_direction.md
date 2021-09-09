---
UID: NE:dot11wificxtypes._WDI_CIPHER_KEY_DIRECTION
tech.root: netvista
title: WDI_CIPHER_KEY_DIRECTION (dot11wificxtypes.h)
ms.date: 07/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CIPHER_KEY_DIRECTION enum defines the traffic directions decrypted by a cipher key.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_CIPHER_KEY_DIRECTION
 - WDI_CIPHER_KEY_DIRECTION
f1_keywords:
 - _WDI_CIPHER_KEY_DIRECTION
 - dot11wificxtypes/_WDI_CIPHER_KEY_DIRECTION
 - WDI_CIPHER_KEY_DIRECTION
 - dot11wificxtypes/WDI_CIPHER_KEY_DIRECTION
dev_langs:
 - c++
---

## -description

The **WDI_CIPHER_KEY_DIRECTION** enumeration defines the traffic directions decrypted by a cipher key.

## -enum-fields

### -field WDI_CIPHER_KEY_DIRECTION_INBOUND:1

The cipher key decrypts packets received from a peer.

### -field WDI_CIPHER_KEY_DIRECTION_OUTBOUND:2

The cipher key decrypts packets transmitted to a peer.

### -field WDI_CIPHER_KEY_DIRECTION_BOTH:3

The cipher key  decrypts packets received from or transmitted to a peer.

## -remarks

The **WDI_CIPHER_KEY_DIRECTION** enumeration is a value in the [WDI_TLV_CIPHER_KEY_TYPE_INFO](/windows-hardware/drivers/netcx/wdi-tlv-cipher-key-type-info) TLV.

## -see-also

[WDI_TLV_CIPHER_KEY_TYPE_INFO](/windows-hardware/drivers/netcx/wdi-tlv-cipher-key-type-info)