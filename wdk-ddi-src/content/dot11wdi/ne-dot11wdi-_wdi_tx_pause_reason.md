---
UID: NE:dot11wdi._WDI_TX_PAUSE_REASON
title: _WDI_TX_PAUSE_REASON (dot11wdi.h)
description: The WDI_TX_PAUSE_REASON enumeration defines the reasons for a TX pause.
old-location: netvista\wdi_tx_pause_reason.htm
tech.root: netvista
ms.assetid: 2585d243-e3b0-414d-a932-28d91b69f1f4
ms.date: 05/02/2018
ms.keywords: WDI_TX_PAUSE_REASON, WDI_TX_PAUSE_REASON enumeration [Network Drivers Starting with Windows Vista], WDI_TX_PAUSE_REASON_CREDIT, WDI_TX_PAUSE_REASON_IHV_END, WDI_TX_PAUSE_REASON_IHV_START, WDI_TX_PAUSE_REASON_NULL, WDI_TX_PAUSE_REASON_PEER_CREATE, WDI_TX_PAUSE_REASON_PS, _WDI_TX_PAUSE_REASON, dot11wdi/WDI_TX_PAUSE_REASON, dot11wdi/WDI_TX_PAUSE_REASON_CREDIT, dot11wdi/WDI_TX_PAUSE_REASON_IHV_END, dot11wdi/WDI_TX_PAUSE_REASON_IHV_START, dot11wdi/WDI_TX_PAUSE_REASON_NULL, dot11wdi/WDI_TX_PAUSE_REASON_PEER_CREATE, dot11wdi/WDI_TX_PAUSE_REASON_PS, netvista.wdi_tx_pause_reason, netvista.wifi_tx_pause_reason
f1_keywords:
 - "dot11wdi/WDI_TX_PAUSE_REASON"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dot11wdi.h
api_name:
- WDI_TX_PAUSE_REASON
product:
- Windows
targetos: Windows
req.typenames: WDI_TX_PAUSE_REASON
---

# _WDI_TX_PAUSE_REASON enumeration


## -description


The WDI_TX_PAUSE_REASON enumeration defines the reasons for a TX pause.


## -enum-fields




### -field WDI_TX_PAUSE_REASON_NULL

Reserved.  This enum value does not represent a valid pause reason code.


### -field WDI_TX_PAUSE_REASON_CREDIT

General reason to use for the exhaustion of some IHV resource.


### -field WDI_TX_PAUSE_REASON_PEER_CREATE

All TIDs on a newly created peer are paused with this reason.  The IHV uses this reason code to restart these TIDs.  This is only applicable when the <b>TargetPriorityQueueing</b> capability is set to false.


### -field WDI_TX_PAUSE_REASON_PS

The peer is in Power Save Mode. This is only applicable when the <b>TargetPriorityQueueing</b> capability is set to false.


### -field WDI_TX_PAUSE_REASON_IHV_START

Inclusive beginning of range of valid pause reasons for IHV use.


### -field WDI_TX_PAUSE_REASON_IHV_END

Inclusive end of range of valid pause reasons for IHV use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>
 

 

