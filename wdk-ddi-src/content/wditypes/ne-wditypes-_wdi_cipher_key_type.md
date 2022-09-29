---
UID: NE:wditypes._WDI_CIPHER_KEY_TYPE
title: _WDI_CIPHER_KEY_TYPE (wditypes.h)
description: The WDI_CIPHER_KEY_TYPE enumeration defines the cipher key types.
old-location: netvista\wdi_cipher_key_type.htm
tech.root: netvista
ms.date: 12/28/2021
keywords: ["WDI_CIPHER_KEY_TYPE enumeration"]
ms.keywords: WDI_CIPHER_KEY_TYPE, WDI_CIPHER_KEY_TYPE enumeration [Device and Driver Installation], WDI_CIPHER_KEY_TYPE_GROUP_KEY, WDI_CIPHER_KEY_TYPE_IGTK, WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY, _WDI_CIPHER_KEY_TYPE, netvista.wdi_cipher_key_type, netvista.wifi_cipher_key_type, wditypes/WDI_CIPHER_KEY_TYPE, wditypes/WDI_CIPHER_KEY_TYPE_GROUP_KEY, wditypes/WDI_CIPHER_KEY_TYPE_IGTK, wditypes/WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY
req.header: wditypes.hpp
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
req.typenames: WDI_CIPHER_KEY_TYPE
f1_keywords:
 - _WDI_CIPHER_KEY_TYPE
 - wditypes/_WDI_CIPHER_KEY_TYPE
 - WDI_CIPHER_KEY_TYPE
 - wditypes/WDI_CIPHER_KEY_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_CIPHER_KEY_TYPE
 - WDI_CIPHER_KEY_TYPE
---

# _WDI_CIPHER_KEY_TYPE enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_CIPHER_KEY_TYPE enumeration defines the cipher key types.

## -enum-fields

### -field WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY:1

The key is a pairwise key to another station.

### -field WDI_CIPHER_KEY_TYPE_GROUP_KEY:2

The key is a group key.

### -field WDI_CIPHER_KEY_TYPE_IGTK:3

The key is an IGTK.

### -field WDI_CIPHER_KEY_TYPE_BIGTK:4

The key is a Beacon Protection Frame Group key.