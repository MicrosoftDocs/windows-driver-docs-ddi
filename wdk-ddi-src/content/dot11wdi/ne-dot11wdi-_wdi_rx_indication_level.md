---
UID: NE:dot11wdi._WDI_RX_INDICATION_LEVEL
title: _WDI_RX_INDICATION_LEVEL (dot11wdi.h)
description: The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.
old-location: netvista\wdi_rx_indication_level.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_RX_INDICATION_LEVEL enumeration"]
ms.keywords: WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC, WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES, WDI_RX_INDICATION_DISPATCH_GENERAL, WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES, WDI_RX_INDICATION_FLAG_RESOURCES, WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES, WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES, WDI_RX_INDICATION_LEVEL, WDI_RX_INDICATION_LEVEL enumeration [Network Drivers Starting with Windows Vista], WDI_RX_INDICATION_PASSIVE, WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES, _WDI_RX_INDICATION_LEVEL, dot11wdi/WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC, dot11wdi/WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES, dot11wdi/WDI_RX_INDICATION_DISPATCH_GENERAL, dot11wdi/WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES, dot11wdi/WDI_RX_INDICATION_FLAG_RESOURCES, dot11wdi/WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES, dot11wdi/WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES, dot11wdi/WDI_RX_INDICATION_LEVEL, dot11wdi/WDI_RX_INDICATION_PASSIVE, dot11wdi/WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES, netvista.wdi_rx_indication_level, netvista.wifi_rx_indication_level
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
req.typenames: WDI_RX_INDICATION_LEVEL
f1_keywords:
 - _WDI_RX_INDICATION_LEVEL
 - dot11wdi/_WDI_RX_INDICATION_LEVEL
 - WDI_RX_INDICATION_LEVEL
 - dot11wdi/WDI_RX_INDICATION_LEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_RX_INDICATION_LEVEL
 - WDI_RX_INDICATION_LEVEL
---

# _WDI_RX_INDICATION_LEVEL enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.

## -enum-fields

### -field WDI_RX_INDICATION_DISPATCH_GENERAL

Used for subsequent data indications in a DPC. <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b> is used for the first data indication of a DPC.

### -field WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC

Used for the first data indication (<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_rx_inorder_data_ind">NdisWdiRxInorderDataIndication</a>) of a DPC.

### -field WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES

Used when making data indications in the context of <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_resume">MiniportWdiRxResume</a>.

### -field WDI_RX_INDICATION_PASSIVE

Used when making data indications at passive level.

### -field WDI_RX_INDICATION_FLAG_RESOURCES

Bitwise OR’d with other enum values to cause RxMgr to set <b>NDIS_RECEIVE_FLAG_RESOURCES</b>.

### -field WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_GENERAL</b>.

### -field WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b>.

### -field WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES</b>.

### -field WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES

Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_PASSIVE</b>.

