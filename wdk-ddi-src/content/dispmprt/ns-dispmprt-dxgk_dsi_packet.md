---
UID: NS:dispmprt._DXGK_DSI_PACKET
title: DXGK_DSI_PACKET
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: An OEM panel driver uses DXGK_DSI_PACKET structures to transmit Digital Serial Interface (DSI) packets to the bus driver (graphics kernel).
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DSI_PACKET, *PDXGK_DSI_PACKET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DSI_PACKET
 - PDXGK_DSI_PACKET
 - DXGK_DSI_PACKET
f1_keywords:
 - _DXGK_DSI_PACKET
 - dispmprt/_DXGK_DSI_PACKET
 - PDXGK_DSI_PACKET
 - dispmprt/PDXGK_DSI_PACKET
 - DXGK_DSI_PACKET
 - dispmprt/DXGK_DSI_PACKET
dev_langs:
 - c++
---

# DXGK_DSI_PACKET structure


## -description

An OEM panel driver uses **DXGK_DSI_PACKET** structures to transmit Digital Serial Interface (DSI) packets to the bus driver (graphics kernel).

## -struct-fields

### -field DataId

8-bit value, where the lower 6 bits form the DataType and the higher 2 bits are VirtualChannel.

### -field DataType

Type of data being transmitted, which implicitly defines the transaction as a read or a write as well as the number of parameters and whether the transaction is formed as a short or long packet.

### -field VirtualChannel

Indicates the sub-unit of the peripheral being addressed. Can be one of 0, 1, 2, or 3.

### -field Data0

8-bit value used in short packets to transfer parameters. Short packets have 0, 1, or 2 bytes of parameters, where the number and meaning is determined by the DataType.

### -field Data1

8-bit value used in short packets to transfer parameters. Short packets have 0, 1, or 2 bytes of parameters, where the number and meaning is determined by the DataType.

### -field LongWriteWordCount

Word count, in bytes, of the Payload for a write long packet.

### -field EccFiller

An 8-bit field which occupies the space that the Error Correction Code (ECC) will take in the sequence of transmitted bytes. The fourth byte of the transmission is always an ECC and for long writes, the payload directly follows the ECC so this filler allows a long write command to be constructed in memory as a complete command. It is the responsibility of the graphics driver to overwrite the filler value with the correct ECC value prior to transmission.

### -field Payload

Array of 8 bytes which allows for sequences of small writes to be sent as an array of packets in the same transmission but limits the size of the data. The final packet in a transmission can append further data in memory directly after the last byte of the embedded Payload. Read packets are only permitted as the last one in a transmission but may be in the form of a long or short packet and either way, the read data should be placed in the Payload buffer, with extra space in the buffer to accommodate longer responses.

## -remarks

The panel driver calls [**IOCTL_MIPI_DSI_TRANSMISSION**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_transmission.md) with an array of **DSI_PACKET** structures in a [**DXGK_DSI_TRANSMISSION**](ns-dispmprt-dxgk_dsi_transmission.md) structure.

## -see-also

[**IOCTL_MIPI_DSI_QUERY_CAPS](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_query_caps.md)

[**IOCTL_MIPI_DSI_RESET**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_reset.md)

[**IOCTL_MIPI_DSI_TRANSMISSION**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_transmission.md)

