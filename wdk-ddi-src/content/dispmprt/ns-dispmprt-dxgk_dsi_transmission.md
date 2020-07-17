---
UID: NS:dispmprt._DXGK_DSI_TRANSMISSION
title: DXGK_DSI_TRANSMISSION
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DSI_TRANSMISSION structure is used to transmit Display Serial Interface (DSI) packets to the bus driver (graphics kernel).
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
req.typenames: DXGK_DSI_TRANSMISSION, *PDXGK_DSI_TRANSMISSION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DSI_TRANSMISSION
 - DXGK_DSI_TRANSMISSION
f1_keywords:
 - dispmprt/_DXGK_DSI_TRANSMISSION
 - dispmprt//DXGK_DSI_TRANSMISSION
 - DXGK_DSI_TRANSMISSION
dev_langs:
 - c++
---

# DXGK_DSI_TRANSMISSION structure

## -description

The DXGK_DSI_TRANSMISSION structure is used to transmit Display Serial Interface (DSI) packets to the bus driver (graphics kernel).

## -struct-fields

### -field TotalBufferSize

Number of bytes in the entire structure including header, commands and payload.

### -field PacketCount

Number of [DXGK_DSI_PACKET](ns-dispmprt-dxgk_dsi_packet.md) elements in the **Packets** array.

### -field FailedPacket

Index, when known, of DXGK_DSI_PACKET in the Packets array that had an error. If not known or there is no detected packet error, the value DXGK_DSI_INVALID_PACKET_INDEX is set.

### -field TransmissionMode

One of the DXGK_MIPI_CONTROL_TRANSMISSIONMODE values.

### -field ReportMipiErrors

If set, graphics driver should request any accumulated MIPI errors in the final command acknowledgement and report them in the MipiErrors field.

### -field ClearMipiErrors

If set and the graphics driver has sent any non-OEM panel initiated commands, the driver should ensure that any accumulated MIPI errors are cleared before starting to send this sequence.

### -field SecondaryPort

Set if the transmission should be sent to a secondary panel, not the primary.

### -field ManufacturingMode

Set to turn off OS validation of DCS commands when the system is in manufacturing mode.

### -field Reserved

Reserved.

### -field ReadWordCount

### -field FinalCommandExtraPayload

### -field MipiErrors

A combination of the following possible error values, indicating the errors reported by communication with the peripheral.

| DXGK_MIPI_DSI_* Error | Meaning |
| --------------------- | ------- |
| DXGK_MIPI_DSI_SOT_ERROR | Possible error in Start of High-Speed transmission leader sequence |
| DXGK_MIPI_DSI_SOT_SYNC_ERROR | Error in Start of High-Speed transmission leader sequence |DXGK_MIPI_DSI_EOT_SYNC_ERROR | Peripheral detected incomplete bytes in High-Speed transmission |
| DXGK_MIPI_DSI_ESCAPE_MODE_ENTRY_COMMAND_ERROR | Error or peripheral does not recognize escape sequence |
| DXGK_MIPI_DSI_LOW_POWER_TRANSMIT_SYNC_ERROR | Peripheral detected incomplete bytes in Low-Speed transmission |
| DXGK_MIPI_DSI_FALSE_CONTROL_ERROR | Peripheral detected error in escape sequence or turnaround sequence |
| DXGK_MIPI_DSI_CONTENTION_DETECTED | Contention detected |
| DXGK_MIPI_DSI_CHECKSUM_ERROR_CORRECTED | A checksum error was detected and corrected |
| DXGK_MIPI_DSI_CHECKSUM_ERROR_NOT_CORRECTED | A checksum error was detected but could not be corrected |
| DXGK_MIPI_DSI_LONG_PACKET_PAYLOAD_CHECKSUM_ERROR | The payload checksum was incorrect for a long packet |
| DXGK_MIPI_DSI_DSI_DATA_TYPE_NOT_RECOGNIZED | Peripheral does not recognize the data type sent to it |
| DXGK_MIPI_DSI_DSI_VC_ID_INVALID | Peripheral was sent a command for a virtual channel which it does not support |
| DXGK_MIPI_DSI_INVALID_TRANSMISSION_LENGTH | Peripheral detected that number of bytes transmitted does not match what was specified in the header |
| DXGK_MIPI_DSI_DSI_PROTOCOL_VIOLATION | Peripheral detected lack of EoTP on a transmission or host failed to signal bus turn-around for a read |

### -field HostErrors

A combination of the DXGK_HOST_DSI_* indicating the errors reported by the graphics driver or OS.

| DXGK_HOST_DSI_* Error | Meaning |
| --------------------- | ------- |
| DXGK_HOST_DSI_DEVICE_NOT_READY | Host detected that a request was made for a device which is not in the correct state to be able to receive the request. |
| DXGK_HOST_DSI_INTERFACE_RESET | The graphics driver detected an error which required a reset of the DSI interface with the panel. The panel driver should verify the device state before resuming normal transmissions. |
| DXGK_HOST_DSI_DEVICE_RESET | The graphics driver detected an error which required a reset of the panel and state should be assumed to have been lost.  The panel driver should reapply any private device state before resuming normal transmissions. |
| DXGK_HOST_DSI_TRANSMISSION_CANCELLED | Host cancelled the transmission, which was in progress, because the bus was needed for higher priority transmissions, such as pixel refresh.  The panel driver needs to ensure that whatever effects a partial transmission could have had are either undone or verified before proceeding with transmissions. If this error happens frequently, it may mean that the transmission is too large to be completed reliably and the panel driver should be changed to split it into multiple transmissions. |
| DXGK_HOST_DSI_TRANSMISSION_DROPPED | Host dropped the transmission before starting it because higher priority transmissions caused the transmission to be delayed beyond the allowed limit.  The panel driver can try the same transmission again, if it is still relevant.  This error indicates that the DSI link bandwidth is inadequate so should not occur in a retail environment.  If the transmission is sufficiently large, this may indicate that the transmission needs to be split in order to succeed reliably. |
| DXGK_HOST_DSI_TRANSMISSION_TIMEOUT | Host detected a hardware timeout while communicating with the peripheral.  The panel driver needs to ensure that whatever effects a partial transmission could have had are either undone or verified before proceeding with transmissions.  Unless the transmission is causing the panel to enter a bad state, there is no mitigation for this in the panel driver, so it should back-off and attempt to resume. |
| DXGK_HOST_DSI_INVALID_TRANSMISSION | OS validation of the DXGK_DSI_TRANSMISSION buffer found errors so the transmission was cancelled without calling the graphics driver or checking for prohibited packets.  This is caused by either an error in the OEM panel driver, or the OS validation.  The `FailedPacket` field indicates the first bad packet if the error is specific to a packet. |
| DXGK_HOST_DSI_OS_REJECTED_PACKET | The OS found packets which are prohibited so the transmission was cancelled without calling the graphics driver. The `FailedPacket` field indicates the first bad packet. |
| DXGK_HOST_DSI_DRIVER_REJECTED_PACKET | The graphics driver found packets which it cannot process safely so the transmission was cancelled without any peripheral interaction. The `FailedPacket` field indicates the first bad packet. |
| DXGK_HOST_DSI_BAD_TRANSMISSION_MODE | The graphics driver was unable to use the DXGK_DSI_CONTROL_TRANSMISSION_MODE specified. The `FailedPacket` field indicates the first packet incompatible with the transmission mode. |

### -field Packets

Array of [**DSI_PACKET**](ns-dispmprt-dxgk_dsi_packet.md) structures.

## -remarks

A DXGK_DSI_TRANSMISSION structure is provided to a graphics driver's [*DxgkDsiTransmission*](nc-dispmprt-dxgkddi_dsitransmission.md) callback function.

## -see-also

[**DXGK_DSI_PACKET**](ns-dispmprt-dxgk_dsi_packet.md)

[**IOCTL_MIPI_DSI_QUERY_CAPS](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_query_caps.md)

[**IOCTL_MIPI_DSI_RESET**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_reset.md)

[**IOCTL_MIPI_DSI_TRANSMISSION**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_transmission.md)
