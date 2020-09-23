---
UID: NS:ntddndis._NDIS_LINK_STATE
title: _NDIS_LINK_STATE (ntddndis.h)
description: The NDIS_LINK_STATE structure specifies the current link state of a miniport adapter.
old-location: netvista\ndis_link_state.htm
tech.root: netvista
ms.assetid: 01d74e69-55fe-4e2e-94ab-7676f9e33403
ms.date: 05/02/2018
keywords: ["NDIS_LINK_STATE structure"]
ms.keywords: "*PNDIS_LINK_STATE, NDIS_LINK_STATE, NDIS_LINK_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_LINK_STATE, PNDIS_LINK_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_LINK_STATE, netvista.ndis_link_state, ntddndis/NDIS_LINK_STATE, ntddndis/PNDIS_LINK_STATE"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
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
req.typenames: NDIS_LINK_STATE, *PNDIS_LINK_STATE
f1_keywords:
 - _NDIS_LINK_STATE
 - ntddndis/_NDIS_LINK_STATE
 - PNDIS_LINK_STATE
 - ntddndis/PNDIS_LINK_STATE
 - NDIS_LINK_STATE
 - ntddndis/NDIS_LINK_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_LINK_STATE
---

# _NDIS_LINK_STATE structure


## -description

The <b>NDIS_LINK_STATE</b> structure specifies the current link state of a miniport adapter.

## -struct-fields

### -field Header

The 
      <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
 <b>NDIS_LINK_STATE</b> structure. Set the 
      <b>Type</b> member of the structure that 
      <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
      <b>Revision</b> member to NDIS_LINK_STATE_REVISION_1, and the 
      <b>Size</b> member to NDIS_SIZEOF_LINK_STATE_REVISION_1.

### -field MediaConnectState

The media connect state for the miniport adapter. For more information, see  
      <a href="/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
 OID_GEN_MEDIA_CONNECT_STATUS_EX</a> OID.

### -field MediaDuplexState

The media duplex state for the miniport adapter. For more information, see <a href="/windows-hardware/drivers/network/oid-gen-media-duplex-state">
 OID_GEN_MEDIA_DUPLEX_STATE</a> OID.

### -field XmitLinkSpeed

The current transmit link speed of the miniport adapter in bits per second. For more information, see <a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>.
 

<div class="alert"><b>Note</b>  A value of NDIS_LINK_SPEED_UNKNOWN indicates that the
 transmit link speed is unknown.</div>
<div> </div>

### -field RcvLinkSpeed

The current receive link speed of the miniport adapter in bits per second. For more information, see <a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>.

 

<div class="alert"><b>Note</b>  A value of NDIS_LINK_SPEED_UNKNOWN indicates that the
 receive link speed is unknown.</div>
<div> </div>

### -field PauseFunctions

The type of support for the IEEE 802.3 pause frames. This member must be one of the following
 pause functions:
      





#### NdisPauseFunctionsUnsupported

the miniport adapter or link partner does not support pause frames.



#### NdisPauseFunctionsSendOnly

the miniport adapter and link partner support only sending pause frames from the miniport adapter to the link
 partner.



#### NdisPauseFunctionsReceiveOnly

the miniport adapter and link partner support only sending pause frames from the link partner to the miniport adapter



#### NdisPauseFunctionsSendAndReceive

the miniport adapter and link partner support sending and receiving pause frames in both transmit and
 receive directions.



#### NdisPauseFunctionsUnknown

Pause frame negotiation is in progress. The pause frame support that the link partner provides
 is unknown.

### -field AutoNegotiationFlags

The auto-negotiation settings for the miniport adapter. This member is created from a bitwise OR
 of the following flags:
      





#### NDIS_LINK_STATE_XMIT_LINK_SPEED_AUTO_NEGOTIATED

the miniport adapter has auto-negotiated the transmit link speed with the link partner.



#### NDIS_LINK_STATE_RCV_LINK_SPEED_AUTO_NEGOTIATED

the miniport adapter has auto-negotiated the receive link speed with the link partner.



#### NDIS_LINK_STATE_DUPLEX_AUTO_NEGOTIATED

the miniport adapter has auto-negotiated the duplex state with the link partner.



#### NDIS_LINK_STATE_PAUSE_FUNCTIONS_AUTO_NEGOTIATED

the miniport adapter has auto-negotiated the pause functions with the link partner.

## -remarks

Miniport drivers use the <a href="/windows-hardware/drivers/network/ndis-status-link-state">NDIS_STATUS_LINK_STATE</a> status indication to notify NDIS and overlying drivers that there has been a change in the physical characteristics of a medium.

When it generates this status indication, the driver sets the 
    <b>StatusBuffer</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure to a pointer to an <b>NDIS_LINK_STATE</b> structure.

The miniport driver also returns an <b>NDIS_LINK_STATE</b> structure when it handles an OID query request of <a href="/windows-hardware/drivers/network/oid-gen-link-state">OID_GEN_LINK_STATE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>



<a href="/windows-hardware/drivers/network/ndis-status-link-state">NDIS_STATUS_LINK_STATE</a>



<a href="/windows-hardware/drivers/network/oid-gen-link-speed-ex">OID_GEN_LINK_SPEED_EX</a>



<a href="/windows-hardware/drivers/network/oid-gen-link-state">OID_GEN_LINK_STATE</a>



<a href="/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
 OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="/windows-hardware/drivers/network/oid-gen-media-duplex-state">
 OID_GEN_MEDIA_DUPLEX_STATE</a>