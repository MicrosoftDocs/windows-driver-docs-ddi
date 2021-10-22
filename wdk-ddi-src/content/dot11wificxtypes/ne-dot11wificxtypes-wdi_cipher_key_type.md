---
UID: NE:dot11wificxtypes._WDI_CIPHER_KEY_TYPE
tech.root: netvista
title: WDI_CIPHER_KEY_TYPE
ms.date: 07/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CIPHER_KEY_TYPE enum defines the cipher key types.
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
 - _WDI_CIPHER_KEY_TYPE
 - WDI_CIPHER_KEY_TYPE
f1_keywords:
 - _WDI_CIPHER_KEY_TYPE
 - dot11wificxtypes/_WDI_CIPHER_KEY_TYPE
 - WDI_CIPHER_KEY_TYPE
 - dot11wificxtypes/WDI_CIPHER_KEY_TYPE
dev_langs:
 - c++
---


## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_CIPHER_KEY_TYPE** enumeration defines the cipher key types.

## -enum-fields

### -field WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY:1

The key is a pairwise key to another station.

### -field WDI_CIPHER_KEY_TYPE_GROUP_KEY:2

The key is a group key.

### -field WDI_CIPHER_KEY_TYPE_IGTK:3

The key is an IGTK.

### -field WDI_CIPHER_KEY_TYPE_BIGTK:3

The key is a Beacon Protection Frame Group key.

## -remarks

The **WDI_CIPHER_KEY_TYPE** enumeration is a value in the [WDI_TLV_CIPHER_KEY_TYPE_INFO](/windows-hardware/drivers/netcx/wdi-tlv-cipher-key-type-info) TLV.

## -see-also

[WDI_TLV_CIPHER_KEY_TYPE_INFO](/windows-hardware/drivers/netcx/wdi-tlv-cipher-key-type-info)
