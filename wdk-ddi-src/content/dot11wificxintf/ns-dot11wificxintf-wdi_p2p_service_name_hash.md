---
UID: NS:dot11wificxintf._WDI_P2P_SERVICE_NAME_HASH
tech.root: netvista
title: WDI_P2P_SERVICE_NAME_HASH (dot11wificxintf.h)
ms.date: 06/24/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_SERVICE_NAME_HASH struct defines a hash of a WFDS Service Name.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxintf.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_P2P_SERVICE_NAME_HASH, *PWDI_P2P_SERVICE_NAME_HASH
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxintf.h
api_name:
 - _WDI_P2P_SERVICE_NAME_HASH
 - PWDI_P2P_SERVICE_NAME_HASH
 - WDI_P2P_SERVICE_NAME_HASH
f1_keywords:
 - _WDI_P2P_SERVICE_NAME_HASH
 - dot11wificxintf/_WDI_P2P_SERVICE_NAME_HASH
 - PWDI_P2P_SERVICE_NAME_HASH
 - dot11wificxintf/PWDI_P2P_SERVICE_NAME_HASH
 - WDI_P2P_SERVICE_NAME_HASH
 - dot11wificxintf/WDI_P2P_SERVICE_NAME_HASH
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is now in maintenance mode and will only receive high priority fixes.

The **WDI_P2P_SERVICE_NAME_HASH** structure defines a hash of a WFDS Service Name.

## -struct-fields

### -field Hash

Hash of a WFDS Service Name. This may also be a hash of an ASP2 Service Type or ASP2 Service Type and Instance Name.

## -remarks

The **WDI_P2P_SERVICE_NAME_HASH** structure is a value in the [**WDI_TLV_P2P_SERVICE_NAME_HASH**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-service-name-hash) TLV.

## -see-also

[**WDI_TLV_P2P_SERVICE_NAME_HASH**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-service-name-hash)