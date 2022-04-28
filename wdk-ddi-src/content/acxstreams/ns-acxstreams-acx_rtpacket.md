---
UID: NS:acxstreams._ACX_RTPACKET
tech.root: audio
title: ACX_RTPACKET
ms.date: 07/07/2021
targetos: Windows
description: The ACX_RTPACKET structure represents a single allocated packet. The PacketBuffer can be a WDFMEMORY handle, an MDL, or a Buffer. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_RTPACKET, *PACX_RTPACKET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACX_RTPACKET
 - PACX_RTPACKET
 - ACX_RTPACKET
f1_keywords:
 - _ACX_RTPACKET
 - acxstreams/_ACX_RTPACKET
 - PACX_RTPACKET
 - acxstreams/PACX_RTPACKET
 - ACX_RTPACKET
 - acxstreams/ACX_RTPACKET
dev_langs:
 - c++
---

## -description

The ACX_RTPACKET structure represents a single allocated packet. The PacketBuffer can be a WDFMEMORY handle, an Memory Descriptor List (MDL), or a Buffer.  

## -struct-fields

### -field Size

The size of the ACX_RTPACKET structure in bytes.

### -field RtPacketBuffer

A [WDF_MEMORY_DESCRIPTOR](/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor) structure that is used as a buffer.

### -field RtPacketOffset

TBD - The RtPacket Offset in bytes.This is a zero based location.

### -field RtPacketSize

The RtPacket Size in Bytes.

## -remarks

## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic