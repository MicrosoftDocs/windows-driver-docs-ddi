---
UID: NS:ntddvdeo._MIPI_DSI_TRANSMISSION
title: MIPI_DSI_TRANSMISSION
description: Mipi (mobile industry processor interface) DSI-2 (display serial interface) transmission.
tech.root: display
ms.date: 04/04/2019
keywords: ["MIPI_DSI_TRANSMISSION structure"]
f1_keywords:
 - "ntddvdeo/MIPI_DSI_TRANSMISSION"
 - "MIPI_DSI_TRANSMISSION"
ms.keywords: MIPI_DSI_TRANSMISSION, MIPI_DSI_TRANSMISSION, *PMIPI_DSI_TRANSMISSION_OUTPUT, MIPI_DSI_TRANSMISSION_INPUT, *PMIPI_DSI_TRANSMISSION_INPUT, MIPI_DSI_TRANSMISSION_OUTPUT
req.header: ntddvdeo.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: MIPI_DSI_TRANSMISSION
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddvdeo.h
api_name: 
 - MIPI_DSI_TRANSMISSION
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# MIPI_DSI_TRANSMISSION structure

## -description

The **MIPI_DSI_TRANSMISSION** structure is used to describe a MIPI (Mobile Industry Processor Interface) DSI (Display Serial Interface) transmission request that contains one or more DSI packets to be sent to the display device.

## -struct-fields

### -field TotalBufferSize

The total size of the buffer that contains the transmission request, in bytes.

### -field PacketCount

The number of packets in the transmission request.

### -field FailedPacket

Failed packet.

### -field TransmissionMode

Transmission mode.

### -field ReportMipiErrors

Report MIPI errors.

### -field ClearMipiErrors

Clear MIPI errors.

### -field SecondaryPort

Secondary port.

### -field Reserved

Reserved.

### -field ReadWordCount

Read word count.

### -field FinalCommandExtraPayload

Final command extra payload.

### -field MipiErrors

MIPI errors.

### -field HostErrors

Host errors.

### -field Packets
 
Packets.

## -remarks

## -see-also
