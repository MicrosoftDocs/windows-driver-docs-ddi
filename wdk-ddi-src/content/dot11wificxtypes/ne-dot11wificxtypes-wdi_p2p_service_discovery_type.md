---
UID: NE:dot11wificxtypes._WDI_P2P_SERVICE_DISCOVERY_TYPE
tech.root: netvista
title: WDI_P2P_SERVICE_DISCOVERY_TYPE (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_SERVICE_DISCOVERY_TYPE enum defines the types of service discovery.
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
 - _WDI_P2P_SERVICE_DISCOVERY_TYPE
 - WDI_P2P_SERVICE_DISCOVERY_TYPE
f1_keywords:
 - _WDI_P2P_SERVICE_DISCOVERY_TYPE
 - dot11wificxtypes/_WDI_P2P_SERVICE_DISCOVERY_TYPE
 - WDI_P2P_SERVICE_DISCOVERY_TYPE
 - dot11wificxtypes/WDI_P2P_SERVICE_DISCOVERY_TYPE
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_P2P_SERVICE_DISCOVERY_TYPE** enumeration defines the types of service discovery.

## -enum-fields

### -field WDI_P2P_SERVICE_DISCOVERY_TYPE_NO_SERVICE_DISCOVERY:1

The adapter should only do a WFD discovery for WFD devices.  It should not encode service hashes in the P2P IEs.

### -field WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_NAME_ONLY:2

The adapter encodes service hashes in the P2P IEs during probe requests and indicates probe responses.  It does not perform any GAS queries for service information.

### -field WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_INFORMATION:3

The adapter encodes the service hashes in the IEs, tracks the service names from the probe responses, and does GAS queries to get service information for each responding device.  This is only applicable if the adapter supports the P2P Service Information Discovery capability.

### -field WDI_P2P_SERVICE_DISCOVERY_TYPE_MAX_VALUE:0xFFFFFFFF

## -remarks

The **WDI_P2P_SERVICE_DISCOVERY_TYPE** enumeration is a value in the [**WDI_TLV_P2P_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-discover-mode) and [**WDI_TLV_P2P_BACKGROUND_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-background-discover-mode) TLVs.

## -see-also

[**WDI_TLV_P2P_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-discover-mode)

[**WDI_TLV_P2P_BACKGROUND_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-background-discover-mode)
