---
UID: NS:ntddvdeo._MIPI_DSI_TRANSMISSION
title: MIPI_DSI_TRANSMISSION
description: Learn more about the MIPI_DSI_TRANSMISSION structure.
tech.root: display
ms.date: 05/21/2024
keywords: ["MIPI_DSI_TRANSMISSION structure"]
f1_keywords:
 - "ntddvdeo/MIPI_DSI_TRANSMISSION"
 - "MIPI_DSI_TRANSMISSION"
ms.keywords: MIPI_DSI_TRANSMISSION, MIPI_DSI_TRANSMISSION, *PMIPI_DSI_TRANSMISSION_OUTPUT, MIPI_DSI_TRANSMISSION_INPUT, *PMIPI_DSI_TRANSMISSION_INPUT, MIPI_DSI_TRANSMISSION_OUTPUT
req.header: ntddvdeo.h
req.construct-type: structure
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

# MIPI_DSI_TRANSMISSION structure (ntddvdeo.h)



## -description

The **MIPI_DSI_TRANSMISSION** structure is used to describe a MIPI (Mobile Industry Processor Interface) DSI (Display Serial Interface) transmission request that contains one or more DSI packets to be sent to the display device.

## -struct-fields

### -field TotalBufferSize

[in] The total size of the buffer that contains the transmission request, in bytes.

### -field PacketCount

[in] The number of packets in the transmission request.

### -field FailedPacket

[out] Index of the first failed packet in the transmission, if any failures occur.

### -field TransmissionMode

[in] Transmission mode.

### -field ReportMipiErrors

[in] When set, indicates that MIPI protocol errors should be reported.

### -field ClearMipiErrors

[in] When set, indicates that MIPI protocol errors should be cleared after being reported.

### -field SecondaryPort

[in] Indicates whether the transmission is for a secondary port.

### -field ManufacturingMode

[in] Indicates whether the transmission is happening in a special manufacturing mode.

### -field Reserved

Reserved.

### -field ReadWordCount

[out] Number of words read during a read operation.

### -field FinalCommandExtraPayload

[in] Size of any extra payload that should be sent with the final command.

### -field MipiErrors

[out] Errors reported by the MIPI DSI hardware, if any.

### -field HostErrors

[out] Errors reported by the host processor or controller that is managing the transmission, if any.

### -field Packets

Array of **PacketCount** [**MIPI_DSI_PACKET**](ns-ntddvdeo-mipi_dsi_packet.md) structures that describe the packets to be transmitted/modified.

## -remarks

## -see-also
