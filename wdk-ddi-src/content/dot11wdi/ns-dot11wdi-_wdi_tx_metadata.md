---
UID: NS:dot11wdi._WDI_TX_METADATA
title: _WDI_TX_METADATA
author: windows-driver-content
description: The WDI_TX_METADATA structure defines the TX metadata.
old-location: netvista\wdi_tx_metadata.htm
old-project: netvista
ms.assetid: 21833980-0098-43c2-822c-9d8292f7120a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PWDI_TX_METADATA, WDI_TX_METADATA structure [Network Drivers Starting with Windows Vista], PWDI_TX_METADATA structure pointer [Network Drivers Starting with Windows Vista], netvista.wifi_tx_metadata, dot11wdi/PWDI_TX_METADATA, dot11wdi/WDI_TX_METADATA, PWDI_TX_METADATA, WDI_TX_METADATA, netvista.wdi_tx_metadata, _WDI_TX_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	dot11wdi.h
apiname: 
-	WDI_TX_METADATA
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# _WDI_TX_METADATA structure


## -description


The 
  WDI_TX_METADATA structure defines the TX metadata.


## -syntax


````
typedef struct _WDI_TX_METADATA {
  WDI_PORT_ID               PortID;
  WDI_PEER_ID               PeerID;
  WDI_EXTENDED_TID          ExTID;
  BOOLEAN                   IsUnicast;
  BOOLEAN                   bAllowLegacyRates;
  UINT16                    Ethertype;
  BOOLEAN                   bTxCompleteRequired;
  UINT8                     PnLength;
  UINT16                    TxCost;
  WDI_EXEMPTION_ACTION_TYPE ExemptionAction;
  WDI_TXRX_MPDU_PN          MpduPn;
  UINT64                    ReplayIHVReserved0;
  UINT64                    ReplayIHVReserved1;
  UINT16                    SeqCtl;
  UINT16                    wPad;
} WDI_TX_METADATA, *PWDI_TX_METADATA;
````


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

Specifies if an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a> is required for this frame.


### -field PnLength

Specifies the PnLength for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.


### -field TxCost

Specifies the number of credits required to dequeue the frame.


### -field ExemptionAction

Specifies the <a href="..\dot11wdi\ne-dot11wdi-_wdi_exemption_action_type.md">WDI_EXEMPTION_ACTION_TYPE</a> value for this frame.


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

<a href="..\dot11wdi\ne-dot11wdi-_wdi_exemption_action_type.md">WDI_EXEMPTION_ACTION_TYPE</a>

<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_TX_METADATA structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

