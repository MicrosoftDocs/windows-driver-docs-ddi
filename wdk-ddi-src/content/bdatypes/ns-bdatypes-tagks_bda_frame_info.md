---
UID: NS:bdatypes.tagKS_BDA_FRAME_INFO
title: tagKS_BDA_FRAME_INFO (bdatypes.h)
description: The KS_BDA_FRAME_INFO structure describes BDA extensions to the KSSTREAM_HEADER structure, which describes a packet of data to be read from or written to a streaming driver pin.
old-location: stream\ks_bda_frame_info.htm
tech.root: stream
ms.assetid: df261323-f372-49e7-990a-03c1c5cb743d
ms.date: 04/23/2018
keywords: ["tagKS_BDA_FRAME_INFO structure"]
ms.keywords: "*PKS_BDA_FRAME_INFO, KS_BDA_FRAME_INFO, KS_BDA_FRAME_INFO structure [Streaming Media Devices], PKS_BDA_FRAME_INFO, PKS_BDA_FRAME_INFO structure pointer [Streaming Media Devices], bdaref_62fe9ca5-dca5-4287-83e8-59667d70d953.xml, bdatypes/KS_BDA_FRAME_INFO, bdatypes/PKS_BDA_FRAME_INFO, stream.ks_bda_frame_info, tagKS_BDA_FRAME_INFO"
req.header: bdatypes.h
req.include-header: Bdamedia.h
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
req.typenames: KS_BDA_FRAME_INFO, *PKS_BDA_FRAME_INFO
f1_keywords:
 - tagKS_BDA_FRAME_INFO
 - bdatypes/tagKS_BDA_FRAME_INFO
 - PKS_BDA_FRAME_INFO
 - bdatypes/PKS_BDA_FRAME_INFO
 - KS_BDA_FRAME_INFO
 - bdatypes/KS_BDA_FRAME_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdatypes.h
api_name:
 - KS_BDA_FRAME_INFO
---

# tagKS_BDA_FRAME_INFO structure


## -description

The KS_BDA_FRAME_INFO structure describes BDA extensions to the KSSTREAM_HEADER structure, which describes a packet of data to be read from or written to a streaming driver pin.

## -struct-fields

### -field ExtendedHeaderSize

Size, in bytes, of the BDA extensions described in this extended header structure.

### -field dwFrameFlags

Flags specific to BDA extensions.

### -field ulEvent

Identifier of an event.

### -field ulChannelNumber

Channel number of a television program.

### -field ulSubchannelNumber

Subchannel number of a television program.

### -field ulReason

Identifies the reason the packet was transferred.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a>

