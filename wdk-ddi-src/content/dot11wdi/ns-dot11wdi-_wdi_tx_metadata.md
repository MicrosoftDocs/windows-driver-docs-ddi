---
UID: NS:dot11wdi._WDI_TX_METADATA
title: _WDI_TX_METADATA (dot11wdi.h)
description: The WDI_TX_METADATA structure defines the TX metadata.
old-location: netvista\wdi_tx_metadata.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_TX_METADATA structure"]
ms.keywords: "*PWDI_TX_METADATA, PWDI_TX_METADATA, PWDI_TX_METADATA structure pointer [Network Drivers Starting with Windows Vista], WDI_TX_METADATA, WDI_TX_METADATA structure [Network Drivers Starting with Windows Vista], _WDI_TX_METADATA, dot11wdi/PWDI_TX_METADATA, dot11wdi/WDI_TX_METADATA, netvista.wdi_tx_metadata, netvista.wifi_tx_metadata"
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
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
f1_keywords:
 - _WDI_TX_METADATA
 - dot11wdi/_WDI_TX_METADATA
 - PWDI_TX_METADATA
 - dot11wdi/PWDI_TX_METADATA
 - WDI_TX_METADATA
 - dot11wdi/WDI_TX_METADATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_TX_METADATA
 - PWDI_TX_METADATA
 - WDI_TX_METADATA
---

# _WDI_TX_METADATA structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  WDI_TX_METADATA structure defines the TX metadata.

## -struct-fields

### -field PortID

Port ID of the frame.

### -field PeerID

Peer ID of the frame (only if <b>TargetPriorityQueueing</b> is false).

### -field ExTID

Extended TID of the frame (only if <b>TargetPriorityQueueing</b> is false).

### -field IsUnicast

Specifies if the frame is for a unicast recipient address.

### -field bAllowLegacyRates

Specifies if legacy rates should be used for transmitting the frame.

### -field Ethertype

Specifies the Ethertype of the frame.

### -field bTxCompleteRequired

Specifies if an <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_complete_ind">NdisWdiTxSendCompleteIndication</a> is required for this frame.

### -field PnLength

Specifies the PnLength for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field TxCost

Specifies the number of credits required to dequeue the frame.

### -field ExemptionAction

Specifies the <a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_exemption_action_type">WDI_EXEMPTION_ACTION_TYPE</a> value for this frame.

### -field MpduPn

Specifies the MpduPn for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field ReplayIHVReserved0

Reserved for use by the IHV miniport for Requeued/Replayed TX frames. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field ReplayIHVReserved1

Reserved for use by the IHV miniport for Requeued/Replayed TX frames. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field SeqCtl

Specifies the SeqCtl (if necessary). This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field wPad

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_exemption_action_type">WDI_EXEMPTION_ACTION_TYPE</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>

