---
UID: NE:ntddndis._NDIS_PM_WOL_PACKET
title: _NDIS_PM_WOL_PACKET (ntddndis.h)
description: The NDIS_PM_WOL_PACKET enumeration identifies the type of a wake-on-LAN (WOL) packet.
old-location: netvista\ndis_pm_wol_packet.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_PM_WOL_PACKET enumeration"]
ms.keywords: "*PNDIS_PM_WOL_PACKET, NDIS_PM_WOL_PACKET, NDIS_PM_WOL_PACKET enumeration [Network Drivers Starting with Windows Vista], NdisPMWoLPacketBitmapPattern, NdisPMWoLPacketEapolRequestIdMessage, NdisPMWoLPacketIPv4TcpSyn, NdisPMWoLPacketIPv6TcpSyn, NdisPMWoLPacketMagicPacket, NdisPMWoLPacketMaximum, NdisPMWoLPacketUnspecified, PNDIS_PM_WOL_PACKET, PNDIS_PM_WOL_PACKET enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_WOL_PACKET, miniport_power_management_ref_4788c1ee-7ed8-49f2-950b-7a820223bc32.xml, netvista.ndis_pm_wol_packet, ntddndis/NDIS_PM_WOL_PACKET, ntddndis/NdisPMWoLPacketBitmapPattern, ntddndis/NdisPMWoLPacketEapolRequestIdMessage, ntddndis/NdisPMWoLPacketIPv4TcpSyn, ntddndis/NdisPMWoLPacketIPv6TcpSyn, ntddndis/NdisPMWoLPacketMagicPacket, ntddndis/NdisPMWoLPacketMaximum, ntddndis/NdisPMWoLPacketUnspecified, ntddndis/PNDIS_PM_WOL_PACKET"
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.typenames: NDIS_PM_WOL_PACKET, *PNDIS_PM_WOL_PACKET
f1_keywords:
 - _NDIS_PM_WOL_PACKET
 - ntddndis/_NDIS_PM_WOL_PACKET
 - PNDIS_PM_WOL_PACKET
 - ntddndis/PNDIS_PM_WOL_PACKET
 - NDIS_PM_WOL_PACKET
 - ntddndis/NDIS_PM_WOL_PACKET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_PM_WOL_PACKET
 - PNDIS_PM_WOL_PACKET
 - NDIS_PM_WOL_PACKET
---

# _NDIS_PM_WOL_PACKET enumeration


## -description

The <b>NDIS_PM_WOL_PACKET</b> enumeration identifies the type of a wake-on-LAN (WOL) packet.

## -enum-fields

### -field NdisPMWoLPacketUnspecified

The WOL packet type is not specified.

### -field NdisPMWoLPacketBitmapPattern

Specifies a bitmap pattern. This packet type is specified in the 
     <b>WoLBitMapPattern</b> member of the 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a> structure.

### -field NdisPMWoLPacketMagicPacket

WOL packets based on WOL magic packet. The media access control (MAC) address in the 
     <a href="/windows/deployment/deploy-whats-new">magic packet</a> is the current MAC
     address of the network adapter.

### -field NdisPMWoLPacketIPv4TcpSyn

An IPv4 TCP SYN wake-on-LAN packet pattern. This packet pattern is specified in the 
     <b>IPv4TcpSynParameters</b> member of the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a> structure.

### -field NdisPMWoLPacketIPv6TcpSyn

An IPv6 TCP SYN wake-on-LAN packet pattern. This packet pattern is specified in the 
     <b>IPv6TcpSynParameters</b> member of the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a> structure.

### -field NdisPMWoLPacketEapolRequestIdMessage

Specifies an EAPOL request message packet. This packet type is specified in the 
     <b>EapolRequestIdMessageParameters</b> member of the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a> structure.

### -field NdisPMWoLPacketMaximum

The maximum value for this enumeration. This value might change in future versions of NDIS header
     files and binaries.

## -remarks

The <b>NDIS_PM_WOL_PACKET</b> enumeration is used in the 
    <b>WoLPacketType</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a> structure.

<div class="alert"><b>Note</b>  The <b>NDIS_PM_WOL_PACKET</b> enumeration type specifies packet based wake-on-LAN (WOL)
    patterns. Wake-on-LAN that is based on NETBIOS over TCP is obsolete and, if necessary, it can be set with
    the pattern bitmap method.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_pm_wol_pattern">NDIS_PM_WOL_PATTERN</a>

