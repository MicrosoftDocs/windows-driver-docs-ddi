---
UID: NS:dot11wdi._WDI_RX_METADATA
title: _WDI_RX_METADATA (dot11wdi.h)
description: The WDI_RX_METADATA structure defines the RX metadata.
old-location: netvista\wdi_rx_metadata.htm
tech.root: netvista
ms.assetid: da1ac5d6-fb17-4034-8448-d582bafda870
ms.date: 05/02/2018
keywords: ["WDI_RX_METADATA structure"]
ms.keywords: "*PWDI_RX_METADATA, PWDI_RX_METADATA, PWDI_RX_METADATA structure pointer [Network Drivers Starting with Windows Vista], WDI_RX_METADATA, WDI_RX_METADATA structure [Network Drivers Starting with Windows Vista], _WDI_RX_METADATA, dot11wdi/PWDI_RX_METADATA, dot11wdi/WDI_RX_METADATA, netvista.wdi_rx_metadata, netvista.wifi_rx_metadata"
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
req.typenames: WDI_RX_METADATA, *PWDI_RX_METADATA
f1_keywords:
 - _WDI_RX_METADATA
 - dot11wdi/_WDI_RX_METADATA
 - PWDI_RX_METADATA
 - dot11wdi/PWDI_RX_METADATA
 - WDI_RX_METADATA
 - dot11wdi/WDI_RX_METADATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - WDI_RX_METADATA
---

# _WDI_RX_METADATA structure


## -description

The 
  WDI_RX_METADATA structure defines the RX metadata.

The RX Engine specifies this metadata in the <b>rxMetadata</b> section of the <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_frame_metadata">WDI_FRAME_METADATA</a> buffer attached to each <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> (in MiniportReserved[0]). Each NET_BUFFER_LIST represents an MPDU.  The IHV miniport driver must not allocate a <a href="/windows-hardware/drivers/ddi/windot11/ns-windot11-dot11_extsta_recv_context">DOT11_EXTSTA_RECV_CONTEXT</a> structure as this is handled by WDI.

## -struct-fields

### -field PayloadType

The payload type, specified for each MPDU.

## -see-also

<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_frame_metadata">WDI_FRAME_METADATA</a>