---
UID: NE:wditypes._WDI_RADIO_MEASUREMENT_ACTION
title: _WDI_RADIO_MEASUREMENT_ACTION (wditypes.h)
description: The WDI_RADIO_MEASUREMENT_ACTION enumeration defines the radio measurement actions.
old-location: netvista\wdi_radio_measurement_action.htm
tech.root: netvista
ms.date: 12/28/2021
keywords: ["WDI_RADIO_MEASUREMENT_ACTION enumeration"]
ms.keywords: WDI_RADIO_MEASUREMENT_ACTION, WDI_RADIO_MEASUREMENT_ACTION enumeration [Device and Driver Installation], WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_REQUEST, WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_RESPONSE, _WDI_RADIO_MEASUREMENT_ACTION, netvista.wdi_radio_measurement_action, netvista.wifi_radio_measurement_action, wditypes/WDI_RADIO_MEASUREMENT_ACTION, wditypes/WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_REQUEST, wditypes/WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_RESPONSE
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
req.typenames: WDI_RADIO_MEASUREMENT_ACTION
f1_keywords:
 - _WDI_RADIO_MEASUREMENT_ACTION
 - wditypes/_WDI_RADIO_MEASUREMENT_ACTION
 - WDI_RADIO_MEASUREMENT_ACTION
 - wditypes/WDI_RADIO_MEASUREMENT_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_RADIO_MEASUREMENT_ACTION
 - WDI_RADIO_MEASUREMENT_ACTION
---

# _WDI_RADIO_MEASUREMENT_ACTION enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_RADIO_MEASUREMENT_ACTION enumeration defines the radio measurement actions.

## -enum-fields

### -field WDI_RADIO_MEASUREMENT_ACTION_RADIO_MEASUREMENT_REQUEST:0

### -field WDI_RADIO_MEASUREMENT_ACTION_RADIO_MEASUREMENT_REPORT:1

### -field WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_REQUEST:4

This refers to the neighbor report request action frame sent by the client to the AP.

### -field WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_RESPONSE:5

This refers to the neighbor report response action frame from the AP.
