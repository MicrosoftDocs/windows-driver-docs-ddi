---
UID: NC:dot11wdi.NDIS_WDI_RX_FLUSH_CONFIRM
title: NDIS_WDI_RX_FLUSH_CONFIRM (dot11wdi.h)
description: The NdisWdiRxFlushConfirm callback function indicates completion of a MiniportWdiRxFlush request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing NdisWdiRxFlushConfirm.
old-location: netvista\ndiswdirxflushconfirm.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WDI_RX_FLUSH_CONFIRM callback function"]
ms.keywords: NDIS_WDI_RX_FLUSH_CONFIRM, NDIS_WDI_RX_FLUSH_CONFIRM callback, NdisWdiRxFlushConfirm, NdisWdiRxFlushConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxFlushConfirm, netvista.ndiswdirxflushconfirm
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
 - NDIS_WDI_RX_FLUSH_CONFIRM
 - dot11wdi/NDIS_WDI_RX_FLUSH_CONFIRM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NDIS_WDI_RX_FLUSH_CONFIRM
---

# NDIS_WDI_RX_FLUSH_CONFIRM callback function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The NdisWdiRxFlushConfirm callback function indicates completion of a <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_flush">MiniportWdiRxFlush</a> request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing <i>NdisWdiRxFlushConfirm</i>.

This is a callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.

## -parameters

### -param NdisMiniportDataPathHandle

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_flush">MiniportWdiRxFlush</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>

