---
UID: NS:avcstrm._CIP_HDR2_SYT
title: _CIP_HDR2_SYT (avcstrm.h)
description: The CIP_HDR2_SYT structure describes the second quadlet of a CIP header pair for a DV format stream.
old-location: stream\cip_hdr2_syt.htm
tech.root: stream
ms.assetid: e66b721f-4cc0-4d35-9e24-6d7dd4029ea4
ms.date: 04/23/2018
ms.keywords: "*PCIP_HDR2_SYT, CIP_HDR2_SYT, CIP_HDR2_SYT structure [Streaming Media Devices], PCIP_HDR2_SYT, PCIP_HDR2_SYT structure pointer [Streaming Media Devices], _CIP_HDR2_SYT, avcsref_1ea551ca-5d40-4bc3-bc54-b736fd6a2b23.xml, avcstrm/CIP_HDR2_SYT, avcstrm/PCIP_HDR2_SYT, stream.cip_hdr2_syt"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- avcstrm.h
api_name:
- CIP_HDR2_SYT
product:
- Windows
targetos: Windows
req.typenames: CIP_HDR2_SYT, *PCIP_HDR2_SYT
---

# _CIP_HDR2_SYT structure


## -description


The CIP_HDR2_SYT structure describes the second quadlet of a CIP header pair for a DV format stream.


## -struct-fields




### -field SYT

Lower 16 bits of CYCLE_TIME. This is not used for opening a stream.


### -field RSV

Must be set to 0:0.


### -field STYPE

Specifies the video signal type, which is used for transmitting real time data.


### -field F5060_OR_TSF

Specifies field encoding or time-shift flag depending on the value of FMT. This flag may be either 0 for NTSC or 1 for PAL, or 1 for TimeShiftFlag. This flag has multiple meanings (like a union) depending on the FMT member. If the FMT member indicates DV format, then this is either 50/60 flag (NTSC or PAL); if it is it MPEG-TS, then this is a time-shifting flag.


### -field FMT

CIP format ID. For example, 000000 = DV and 100000 = MPEG2TS. If this is 111111 (no data), then DBS, FN, SPH and DBC (in the first quadlet of the CIP header, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/avcstrm/ns-avcstrm-_cip_hdr1">CIP_HDR1</a>) are ignored.


### -field Bit10

Must be set to 1:0.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/avcstrm/ns-avcstrm-_cip_hdr1">CIP_HDR1</a>
 

 

