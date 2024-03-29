---
UID: NE:wditypes._WDI_WNM_ACTION
title: _WDI_WNM_ACTION (wditypes.h)
description: The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames.
old-location: netvista\wdi_wnm_action.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_WNM_ACTION enumeration"]
ms.keywords: WDI_WNM_ACTION, WDI_WNM_ACTION enumeration [Network Drivers Starting with Windows Vista], WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE, _WDI_WNM_ACTION, netvista.wdi_wnm_action, wditypes/WDI_WNM_ACTION, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE
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
req.typenames: WDI_WNM_ACTION
f1_keywords:
 - _WDI_WNM_ACTION
 - wditypes/_WDI_WNM_ACTION
 - WDI_WNM_ACTION
 - wditypes/WDI_WNM_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_WNM_ACTION
 - WDI_WNM_ACTION
---

# _WDI_WNM_ACTION enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames.

## -enum-fields

### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY

The message is a BSS Transition Management query frame.

### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST

The message is a BSS Transition Management request frame. This is sent by the AP to the client.

### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE

The message is a BSS Transition Management response frame. This is a response to the above request frame from the AP.

