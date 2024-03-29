---
UID: NE:dot11wdi._WDI_OPERATION_MODE
title: _WDI_OPERATION_MODE (dot11wdi.h)
description: The WDI_OPERATION_MODE enumeration defines operation modes.
old-location: netvista\wdi_operation_mode.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_OPERATION_MODE enumeration"]
ms.keywords: WDI_OPERATION_MODE, WDI_OPERATION_MODE enumeration [Network Drivers Starting with Windows Vista], WDI_OPERATION_MODE_P2P_CLIENT, WDI_OPERATION_MODE_P2P_DEVICE, WDI_OPERATION_MODE_P2P_GO, WDI_OPERATION_MODE_STA, _WDI_OPERATION_MODE, dot11wdi/WDI_OPERATION_MODE, dot11wdi/WDI_OPERATION_MODE_P2P_CLIENT, dot11wdi/WDI_OPERATION_MODE_P2P_DEVICE, dot11wdi/WDI_OPERATION_MODE_P2P_GO, dot11wdi/WDI_OPERATION_MODE_STA, netvista.wdi_operation_mode, netvista.wifi_operation_mode
req.header: dot11wdi.h
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
req.typenames: WDI_OPERATION_MODE
f1_keywords:
 - _WDI_OPERATION_MODE
 - dot11wdi/_WDI_OPERATION_MODE
 - WDI_OPERATION_MODE
 - dot11wdi/WDI_OPERATION_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_OPERATION_MODE
 - WDI_OPERATION_MODE
---

# _WDI_OPERATION_MODE enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_OPERATION_MODE enumeration defines operation modes.

## -enum-fields

### -field WDI_OPERATION_MODE_STA

Infrastructure client.

### -field WDI_OPERATION_MODE_P2P_DEVICE

Wi-Fi Direct Device.

### -field WDI_OPERATION_MODE_P2P_CLIENT

Wi-Fi Direct Client.

### -field WDI_OPERATION_MODE_P2P_GO

Wi-Fi Direct Group Owner.

