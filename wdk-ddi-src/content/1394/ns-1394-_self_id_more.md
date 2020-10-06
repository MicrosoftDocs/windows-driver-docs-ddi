---
UID: NS:1394._SELF_ID_MORE
title: _SELF_ID_MORE (1394.h)
description: The SELF_ID_MORE structure contains a raw packet one, two, or three self-ID packet. See the IEEE 1394 specification for details.
old-location: ieee\self_id_more.htm
tech.root: IEEE
ms.assetid: d3c164a6-4830-4f1f-9fa5-5cd61e796e31
ms.date: 02/15/2018
keywords: ["SELF_ID_MORE structure"]
ms.keywords: "*PSELF_ID_MORE, 1394/PSELF_ID_MORE, 1394/SELF_ID_MORE, 1394stct_cbfa017d-065b-45ce-ae08-6a6589c6b477.xml, IEEE.self_id_more, PSELF_ID_MORE, PSELF_ID_MORE structure pointer [Buses], SELF_ID_MORE, SELF_ID_MORE structure [Buses], _SELF_ID_MORE"
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: SELF_ID_MORE, *PSELF_ID_MORE
f1_keywords:
 - _SELF_ID_MORE
 - 1394/_SELF_ID_MORE
 - PSELF_ID_MORE
 - 1394/PSELF_ID_MORE
 - SELF_ID_MORE
 - 1394/SELF_ID_MORE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - SELF_ID_MORE
---

# _SELF_ID_MORE structure


## -description

The SELF_ID_MORE structure contains a raw packet one, two, or three self-ID packet. See the IEEE 1394 specification for details.

## -struct-fields

### -field SID_Phys_ID

Specifies the device node number. This member specifies bits 0-10 of the node address. This member contains bits 0-5 of byte 0 of the self ID packet.

### -field SID_Packet_ID

Must be PHY_PACKET_ID_SELF_ID. This member specifies bits 0-10 of the node address. This member contains bits 6-7 of byte 0 of the self ID packet.

### -field SID_PortA

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 0-1 of byte 1 of the self ID packet.

### -field SID_Reserved2

Reserved. This member contains bits 2-3 of byte 1 of the self ID packet.

### -field SID_Sequence

Specifies the packet number in sequence (the first SELF_ID_MORE packet is packet zero). This member contains bits 4-5 of byte 1 of the self ID packet.

### -field SID_One

Always a 1. This member contains bit 6 of byte 1 of the self ID packet.

### -field SID_PortE

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member specifies bits 0-1 of byte 2 of the self ID packet.

### -field SID_PortD

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member specifies bits 2-3 of byte 2 of the self ID packet.

### -field SID_PortC

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 4-5 of byte 2 of the self ID packet.

### -field SID_PortB

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 6-7 of byte 2 of the self ID packet.

### -field SID_More_Packets

One if this packet will be followed by more SELF_ID_MORE packets, zero otherwise. This member contains bit 0 of byte 3 of the self ID packet.

### -field SID_Reserved3

Reserved. This member contains bit 1 of byte 3 of the self ID packet.

### -field SID_PortH

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 2-3 of byte 3 of the self ID packet.

### -field SID_PortG

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 4-5 of byte 3 of the self ID packet.

### -field SID_PortF

Specifies port status. Possible values are:

SELF_ID_CONNECTED_TO_CHILD

SELF_ID_CONNECTED_TO_PARENT

SELF_ID_NOT_CONNECTED

SELF_ID_NOT_PRESENT

This member contains bits 6-7 of byte 3 of the self ID packet.

## -remarks

This structure corresponds to self ID packet 1, as described in the <i>P1394a</i> specification. Note that type 2 self ID packets are identical to type 1 packets, except that the last five fields are replaced by a reserved area. The SELF_ID_MORE structure can be used to access all of the significant information in both type 1 and type 2 self ID packets.

## -see-also

<a href="/windows-hardware/drivers/ddi/1394/ns-1394-_topology_map">TOPOLOGY_MAP</a>