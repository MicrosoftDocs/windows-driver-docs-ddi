---
UID: NS:acxstreams._ACX_RTPACKET
tech.root: audio
title: ACX_RTPACKET
ms.date: 07/07/2021
targetos: Windows
description: The ACX_RTPACKET structure represents a single allocated packet. The PacketBuffer must be an MDL.
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

The ACX_RTPACKET structure represents a single allocated packet. The PacketBuffer must be a Memory Descriptor List (MDL).  

## -struct-fields

### -field Size

The size of the ACX_RTPACKET structure in bytes.

### -field RtPacketBuffer

A [WDF_MEMORY_DESCRIPTOR](/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor) structure that is used as a buffer. Only WdfMemoryDescriptorTypeMdl and WdfMemoryDescriptorTypeInvalid are supported.

The RtPacketBuffer must be valid for the first ACX_RTPACKET in an array of ACX_RTPACKET structures. The RtPacketBuffer must be PAGE-aligned with a PAGE-aligned size.

### -field RtPacketOffset

The zero-based offset in bytes in the RtPacketBuffer at which the actual audio packet starts.

### -field RtPacketSize

The size in bytes of the allocated packet.

## -remarks

The ACX framework currenlty only supports WdfMemoryDescriptorTypeMdl packet buffers.

See documentation for [EVT_ACX_STREAM_ALLOCATE_RTPACKETS](nc-acxstreams-evt_acx_stream_allocate_rtpackets.md) for details on allocating ACX_RTPACKET structures.

## -see-also

[acxstreams.h header](index.md)
[EVT_ACX_STREAM_ALLOCATE_RTPACKETS](nc-acxstreams-evt_acx_stream_allocate_rtpackets.md)

READY2GO
