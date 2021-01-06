---
UID: NS:avcstrm._CIP_HDR2_MPEGTS
title: _CIP_HDR2_MPEGTS (avcstrm.h)
description: The CIP_HDR2_MPEGTS structure describes the second quadlet of a CIP header pair for an MPEGTS format stream.
old-location: stream\cip_hdr2_mpegts.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["CIP_HDR2_MPEGTS structure"]
ms.keywords: "*PCIP_HDR2_MPEGTS, CIP_HDR2_MPEGTS, CIP_HDR2_MPEGTS structure [Streaming Media Devices], PCIP_HDR2_MPEGTS, PCIP_HDR2_MPEGTS structure pointer [Streaming Media Devices], _CIP_HDR2_MPEGTS, avcsref_80577192-cbb5-401a-a840-5970841111ab.xml, avcstrm/CIP_HDR2_MPEGTS, avcstrm/PCIP_HDR2_MPEGTS, stream.cip_hdr2_mpegts"
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
req.typenames: CIP_HDR2_MPEGTS, *PCIP_HDR2_MPEGTS
f1_keywords:
 - _CIP_HDR2_MPEGTS
 - avcstrm/_CIP_HDR2_MPEGTS
 - PCIP_HDR2_MPEGTS
 - avcstrm/PCIP_HDR2_MPEGTS
 - CIP_HDR2_MPEGTS
 - avcstrm/CIP_HDR2_MPEGTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avcstrm.h
api_name:
 - CIP_HDR2_MPEGTS
---

# _CIP_HDR2_MPEGTS structure


## -description

The CIP_HDR2_MPEGTS structure describes the second quadlet of a CIP header pair for an MPEGTS format stream.

## -struct-fields

### -field TSF

Time-shift flag. This is not used for opening a stream.

### -field RSV23bit

Reserved bits. This must be 0. Do not use this.

### -field FMT

CIP format. For example, 000000 = DV and 100000 = MPEGTS.

### -field Bit10

Must be set to 1:0

## -see-also

<a href="/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_cip_hdr1">CIP_HDR1</a>
