---
UID: NE:ntddndis._NDIS_MEDIUM
title: _NDIS_MEDIUM (ntddndis.h)
description: The NDIS_MEDIUM enumeration type identifies the medium types that NDIS drivers support.
old-location: netvista\ndis_medium.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_MEDIUM enumeration"]
ms.keywords: "*PNDIS_MEDIUM, NDIS_MEDIUM, NDIS_MEDIUM enumeration [Network Drivers Starting with Windows Vista], NdisMedium1394, NdisMedium802_3, NdisMedium802_5, NdisMediumArcnet878_2, NdisMediumArcnetRaw, NdisMediumAtm, NdisMediumBpc, NdisMediumCoWan, NdisMediumDix, NdisMediumFddi, NdisMediumIP, NdisMediumInfiniBand, NdisMediumIrda, NdisMediumLocalTalk, NdisMediumLoopback, NdisMediumMax, NdisMediumNative802_11, NdisMediumTunnel, NdisMediumWan, NdisMediumWirelessWan, PNDIS_MEDIUM, PNDIS_MEDIUM enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_MEDIUM, netvista.ndis_medium, ntddndis/NDIS_MEDIUM, ntddndis/NdisMedium1394, ntddndis/NdisMedium802_3, ntddndis/NdisMedium802_5, ntddndis/NdisMediumArcnet878_2, ntddndis/NdisMediumArcnetRaw, ntddndis/NdisMediumAtm, ntddndis/NdisMediumBpc, ntddndis/NdisMediumCoWan, ntddndis/NdisMediumDix, ntddndis/NdisMediumFddi, ntddndis/NdisMediumIP, ntddndis/NdisMediumInfiniBand, ntddndis/NdisMediumIrda, ntddndis/NdisMediumLocalTalk, ntddndis/NdisMediumLoopback, ntddndis/NdisMediumMax, ntddndis/NdisMediumNative802_11, ntddndis/NdisMediumTunnel, ntddndis/NdisMediumWan, ntddndis/NdisMediumWirelessWan, ntddndis/PNDIS_MEDIUM, protocol_structures_ref_3b154721-1574-4855-9028-704ce215eb91.xml"
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later.
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
req.typenames: NDIS_MEDIUM, *PNDIS_MEDIUM
f1_keywords:
 - _NDIS_MEDIUM
 - ntddndis/_NDIS_MEDIUM
 - PNDIS_MEDIUM
 - ntddndis/PNDIS_MEDIUM
 - NDIS_MEDIUM
 - ntddndis/NDIS_MEDIUM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_MEDIUM
 - PNDIS_MEDIUM
 - NDIS_MEDIUM
---

# _NDIS_MEDIUM enumeration


## -description

The <b>NDIS_MEDIUM</b> enumeration type identifies the medium types that NDIS drivers support.

## -enum-fields

### -field NdisMedium802_3

Specifies an Ethernet (802.3) network.

### -field NdisMedium802_5

Specifies a Token Ring (802.5) network.

<div class="alert"><b>Note</b>   Not supported in Windows 8 or later.</div>
<div> </div>

### -field NdisMediumFddi

Specifies a Fiber Distributed Data Interface (FDDI) network.

<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumWan

Specifies a wide area network. This type covers various forms of point-to-point and WAN NICs, as
     well as variant address/header formats that must be negotiated between the protocol driver and the
     underlying driver after the binding is established.

### -field NdisMediumLocalTalk

Specifies a LocalTalk network.

### -field NdisMediumDix

Specifies an Ethernet network for which the drivers use the DIX Ethernet header format.

### -field NdisMediumArcnetRaw

Specifies an ARCNET network.

<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumArcnet878_2

Specifies an ARCNET (878.2) network.

<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumAtm

Specifies an ATM network. Connection-oriented client protocol drivers can bind themselves to an
     underlying miniport driver that returns this value. Otherwise, legacy protocol drivers bind themselves
     to the system-supplied LanE intermediate driver, which reports its medium type as either of 
     <b>NdisMedium802_3</b> or 
     <b>NdisMedium802_5</b>, depending on how the LanE driver is configured by the network
     administrator.

### -field NdisMediumWirelessWan

Specifies a wireless network. NDIS 5.X miniport drivers that support wireless LAN (WLAN) or
     wireless WAN (WWAN) packets declare their medium as 
     <b>NdisMedium802_3</b> and emulate Ethernet to higher-level NDIS drivers.
     


<div class="alert"><b>Note</b>  Starting with Windows 7, this media type is supported and can
      be used for Mobile Broadband.</div>
<div> </div>

### -field NdisMediumIrda

Specifies an infrared (IrDA) network.

### -field NdisMediumBpc

Specifies a broadcast PC network.

### -field NdisMediumCoWan

Specifies a wide area network in a connection-oriented environment.

### -field NdisMedium1394

Specifies an IEEE 1394 (fire wire) network. 

<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumInfiniBand

Specifies an InfiniBand network.

### -field NdisMediumTunnel

Specifies a tunnel network.

### -field NdisMediumNative802_11

Specifies a native IEEE 802.11 network.

### -field NdisMediumLoopback

Specifies an NDIS loopback network.

### -field NdisMediumWiMAX

Specifies an IEEE 802.16 WiMAX network.

### -field NdisMediumIP

Specifies a generic medium that is capable of sending and receiving raw IP packets.

### -field NdisMediumMax

A maximum value for testing purposes.

