---
UID: NC:dot11wdi.MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION
title: MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION (dot11wdi.h)
description: NDIS calls the MiniportWdiCancelIdleNotification handler function to notify the WDI miniport driver that NDIS has detected activity on the suspended network adapter.
old-location: netvista\miniportwdicancelidlenotification.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION callback function"]
ms.keywords: MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION, MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION callback, MiniportWdiCancelIdleNotification, MiniportWdiCancelIdleNotification callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiCancelIdleNotification, netvista.miniportwdicancelidlenotification
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
req.typenames: 
f1_keywords:
 - MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION
 - dot11wdi/MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION
---

# MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION callback function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

NDIS calls the MiniportWdiCancelIdleNotification handler function to notify the WDI miniport driver that NDIS has detected activity on the suspended network adapter. Because of this, NDIS cancels the idle notification so that the network adapter can be transitioned to a full-power state.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_CANCEL_IDLE_NOTIFICATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext [in]


The handle to the context area that the miniport driver allocated.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>

