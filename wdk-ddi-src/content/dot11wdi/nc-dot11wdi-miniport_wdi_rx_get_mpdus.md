---
UID: NC:dot11wdi.MINIPORT_WDI_RX_GET_MPDUS
title: MINIPORT_WDI_RX_GET_MPDUS
author: windows-driver-content
description: The MiniportWdiRxGetMpdus handler function returns a NET_BUFFER_LIST chain. Each NET_BUFFER_LIST represents one MPDU.
old-location: netvista\miniportwdirxgetmpdus.htm
old-project: netvista
ms.assetid: 195F4143-4889-4788-BAF5-2F1ED6E4E50A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdirxgetmpdus, MiniportWdiRxGetMpdus callback function [Network Drivers Starting with Windows Vista], MiniportWdiRxGetMpdus, MINIPORT_WDI_RX_GET_MPDUS, MINIPORT_WDI_RX_GET_MPDUS, dot11wdi/MiniportWdiRxGetMpdus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiRxGetMpdus
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_RX_GET_MPDUS callback


## -description


The 
  MiniportWdiRxGetMpdus handler function returns a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain. Each NET_BUFFER_LIST represents one MPDU.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_GET_MPDUS</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_RX_GET_MPDUS MiniportWdiRxGetMpdus;

VOID MiniportWdiRxGetMpdus(
  _In_  TAL_TXRX_HANDLE  MiniportTalTxRxContext,
  _In_  WDI_PEER_ID      PeerId,
  _In_  WDI_EXTENDED_TID ExTid,
  _Out_ PNET_BUFFER_LIST *ppNBL
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PeerId [in]

The peer ID.


### -param ExTid [in]

The extended TID.


### -param *ppNBL [out]

Pointer to a pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain from the IHV miniport.


## -returns


This callback function does not return a value.



## -remarks


If <i>PeerId</i> and <i>ExTid</i> are not wildcards (for example, <i>PeerId</i> is not equal to 0xFFFF, <i>ExTid</i> is not equal to 31), all MPDUs in the chain are of the same peer ID and TID (in this case, TID is a valid 802.11 TID).

Each <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> points to <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures. Each NET_BUFFER structure represents one MSDU.

If an MPDU has an MSDU fragment as payload and defragmentation is not offloaded to target/TAL (or  host-implemented FIPS mode is enabled), the corresponding NET_BUFFER_LIST has one NET_BUFFER that describes the MSDU fragment.

The data offset of each NET_BUFFER must be set to the start of the MAC header.



## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_RX_GET_MPDUS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

