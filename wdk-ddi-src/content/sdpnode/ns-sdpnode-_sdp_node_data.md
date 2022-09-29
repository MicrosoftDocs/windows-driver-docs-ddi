---
UID: NS:sdpnode._SDP_NODE_DATA
title: _SDP_NODE_DATA (sdpnode.h)
description: The SDP_NODE_DATA union holds the data of an element in a tree-based representation of an SDP record.
old-location: bltooth\sdp_node_data.htm
tech.root: bltooth
ms.date: 08/11/2022
keywords: ["SDP_NODE_DATA structure"]
ms.keywords: "*PSDP_NODE_DATA, PSDP_NODE_DATA, PSDP_NODE_DATA union pointer [Bluetooth Devices], SDP_NODE_DATA, SDP_NODE_DATA union [Bluetooth Devices], _SDP_NODE_DATA, bltooth.sdp_node_data, bth_structs_c97da04d-31d0-4e0b-b909-9a1fae7d53dd.xml, sdpnode/PSDP_NODE_DATA, sdpnode/SDP_NODE_DATA"
req.header: sdpnode.h
req.include-header: Sdpnode.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.typenames: SDP_NODE_DATA, *PSDP_NODE_DATA
f1_keywords:
 - _SDP_NODE_DATA
 - sdpnode/_SDP_NODE_DATA
 - PSDP_NODE_DATA
 - sdpnode/PSDP_NODE_DATA
 - SDP_NODE_DATA
 - sdpnode/SDP_NODE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sdpnode.h
api_name:
 - _SDP_NODE_DATA
 - PSDP_NODE_DATA
 - SDP_NODE_DATA
---

# _SDP_NODE_DATA structure

## -description

The SDP_NODE_DATA union holds the data of an element in a tree-based representation of an SDP record.

## -struct-fields

### -field int128

The union member for a 128-bit integer.

### -field uint128

The union member for an unsigned 128-bit integer.

### -field uuid128

The union member for a 128-bit universally unique identifier (UUID).

### -field uuid32

The union member for a 32-bit UUID.

### -field uuid16

The union member for a 16-bit UUID.

### -field int64

The union member for a 64-bit integer.

### -field uint64

The union member for an unsigned 64-bit integer.

### -field int32

The union member for a 32-bit integer.

### -field uint32

The union member for an unsigned 32-bit integer.

### -field int16

The union member for a 16-bit integer.

### -field uint16

The union member for an unsigned 16-bit integer.

### -field int8

The union reserved for an 8-bit integer.

### -field uint8

The union member for an unsigned 8-bit integer.

### -field boolean

The union member for a Boolean value.

### -field string

The union member for a string value.

### -field url

The union member for a URL value.

### -field sequence

An [SDP_NODE_HEADER](./ns-sdpnode-_sdp_node_header.md) structure that references the elements of a sequence.

### -field alternative

An SDP_NODE_HEADER structure that references the elements of an alternate list sequence.

### -field container

A list of pointers to user-mode specific interfaces.

### -field stream

The address of a portion of the original SDP stream that produced the current SDP node.

### -field streamLength

The length of the portion of the original SDP stream that produced the current SDP node.

## -remarks

Each [SDP_NODE](./ns-sdpnode-_sdp_node.md) structure in the tree representation of an SDP record contains a SDP_NODE_HEADER structure and an SDP_NODE_DATA union.

The header specifies the type of data. Driver developers can access links to peer **SDP_NODE** structures by calling the [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure of the header. By evaluating `Node.hdr.Link.Flink`and `Node.hdr.Link.Blink`, drivers can obtain the addresses of peer nodes in the tree. Keep in mind that **LIST_ENTRY** pointers contain the addresses of other LIST_ENTRY structures, and that the profile driver must use the [CONTAINING_RECORD](/windows/win32/api/ntdef/nf-ntdef-containing_record) memory manager macro to extract the address of the containing node record.

The unnamed struct contains the union member for a 128-bit integer.

## -see-also

- [SDP_NODE_HEADER](./ns-sdpnode-_sdp_node_header.md)
- [SDP_NODE](./ns-sdpnode-_sdp_node.md)
- [LIST_ENTRY](/windows/win32/api/ntdef/ns-ntdef-list_entry)
- [CONTAINING_RECORD](/windows/win32/api/ntdef/nf-ntdef-containing_record)
