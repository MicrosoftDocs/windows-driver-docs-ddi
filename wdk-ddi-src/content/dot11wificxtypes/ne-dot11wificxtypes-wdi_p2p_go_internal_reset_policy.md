---
UID: NE:dot11wificxtypes._WDI_P2P_GO_INTERNAL_RESET_POLICY
tech.root: netvista
title: WDI_P2P_GO_INTERNAL_RESET_POLICY (dot11wificxtypes.h)
ms.date: 07/28/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_GO_INTERNAL_RESET_POLICY enum defines the Wi-Fi Direct Group Owner internal reset policies.
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
 - _WDI_P2P_GO_INTERNAL_RESET_POLICY
 - WDI_P2P_GO_INTERNAL_RESET_POLICY
f1_keywords:
 - _WDI_P2P_GO_INTERNAL_RESET_POLICY
 - dot11wificxtypes/_WDI_P2P_GO_INTERNAL_RESET_POLICY
 - WDI_P2P_GO_INTERNAL_RESET_POLICY
 - dot11wificxtypes/WDI_P2P_GO_INTERNAL_RESET_POLICY
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_P2P_GO_INTERNAL_RESET_POLICY** enumeration defines the Wi-Fi Direct Group Owner internal reset policies.

## -enum-fields

### -field WDI_P2P_GO_INTERNAL_RESET_POLICY_USE_LAST_CHANNEL:1

If an internal-to-firmware Group Owner reset is performed, post-reset Group Owner must operate on the same operating channel as before the internal reset operation.

### -field WDI_P2P_GO_INTERNAL_RESET_POLICY_ALLOW_CHANNEL_OPTIMIZATION:2

If an internal-to-firmware Group Owner reset is performed, firmware may freely decide its new operating channel. For example, firmware may choose to minimize channel switching by adopting station port channel. If there is no optimization to be done, fall back to selecting previous operating channel.

### -field WDI_P2P_GO_INTERNAL_RESET_POLICY_MAX:0xFFFFFFFF

## -remarks

The **WDI_P2P_GO_INTERNAL_RESET_POLICY** enum is a value in the [**WDI_TLV_P2P_GO_INTERNAL_RESET_POLICY**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-go-internal-reset-policy) TLV.

## -see-also

[**WDI_TLV_P2P_GO_INTERNAL_RESET_POLICY**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-go-internal-reset-policy)
