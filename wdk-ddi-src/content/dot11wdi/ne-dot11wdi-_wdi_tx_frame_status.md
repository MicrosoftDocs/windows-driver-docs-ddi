---
UID: NE:dot11wdi._WDI_TX_FRAME_STATUS
title: _WDI_TX_FRAME_STATUS (dot11wdi.h)
description: The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values.
old-location: netvista\wdi_tx_frame_status.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_TX_FRAME_STATUS enumeration"]
ms.keywords: WDI_TX_FRAME_STATUS, WDI_TX_FRAME_STATUS enumeration [Network Drivers Starting with Windows Vista], WDI_TxFrameStatus_Discard, WDI_TxFrameStatus_NoAck, WDI_TxFrameStatus_Ok, WDI_TxFrameStatus_SendCancelled, WDI_TxFrameStatus_SendPostponed, WDI_TxFrameStatus_TransferCancelled, WDI_TxFrameStatus_TransferFailed, _WDI_TX_FRAME_STATUS, dot11wdi/WDI_TX_FRAME_STATUS, dot11wdi/WDI_TxFrameStatus_Discard, dot11wdi/WDI_TxFrameStatus_NoAck, dot11wdi/WDI_TxFrameStatus_Ok, dot11wdi/WDI_TxFrameStatus_SendCancelled, dot11wdi/WDI_TxFrameStatus_SendPostponed, dot11wdi/WDI_TxFrameStatus_TransferCancelled, dot11wdi/WDI_TxFrameStatus_TransferFailed, netvista.wdi_tx_frame_status, netvista.wifi_tx_frame_status
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
req.typenames: WDI_TX_FRAME_STATUS
f1_keywords:
 - _WDI_TX_FRAME_STATUS
 - dot11wdi/_WDI_TX_FRAME_STATUS
 - WDI_TX_FRAME_STATUS
 - dot11wdi/WDI_TX_FRAME_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_TX_FRAME_STATUS
 - WDI_TX_FRAME_STATUS
---

# _WDI_TX_FRAME_STATUS enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values.

## -enum-fields

### -field WDI_TxFrameStatus_Ok

Frame transmitted without errors.

### -field WDI_TxFrameStatus_Discard

The frame was discarded to make room for higher priority frames.

### -field WDI_TxFrameStatus_NoAck

Transmission failed after exhausting the maximum number of retries.

### -field WDI_TxFrameStatus_TransferCancelled

TX stop requested.

### -field WDI_TxFrameStatus_SendCancelled

TX stop requested.

### -field WDI_TxFrameStatus_SendPostponed

The frame could not be transmitted at this time (for example, the peer is in PS). The frame should be transferred at a suitable time, when the corresponding TX queue is unpaused. This status is not allowed for targets that have <b>TargetPriorityQueueing</b> set to TRUE.

### -field WDI_TxFrameStatus_TransferFailed

The transfer failed.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>

