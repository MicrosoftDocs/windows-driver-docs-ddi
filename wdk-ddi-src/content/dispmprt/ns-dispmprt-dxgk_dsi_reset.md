---
UID: NS:dispmprt._DXGK_DSI_RESET
title: DXGK_DSI_RESET
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DSI_RESET structure is used with IOCTL_MIPI_DSI_RESET.
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
req.typenames: DXGK_DSI_RESET, *PDXGK_DSI_RESET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DSI_RESET
 - PDXGK_DSI_RESET
 - DXGK_DSI_RESET
f1_keywords:
 - _DXGK_DSI_RESET
 - dispmprt/_DXGK_DSI_RESET
 - PDXGK_DSI_RESET
 - dispmprt/PDXGK_DSI_RESET
 - DXGK_DSI_RESET
 - dispmprt/DXGK_DSI_RESET
dev_langs:
 - c++
---

# DXGK_DSI_RESET structure


## -description

The **DXGK_DSI_RESET** structure is used with [**IOCTL_MIPI_DSI_RESET**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_reset.md).

## -struct-fields

### -field Flags

Reserved. Must be set to zero.

### -field MipiErrors

A combination of the DXGK_DSI_* values indicating the errors reported by communication with the peripheral. Can be one or more of the following values.

| Error | Meaning |
| ----- | ------- |
| DXGK_DSI_SOT_ERROR | Possible error in Start of High-Speed transmission leader sequence |

| DXGK_DSI_SOT_SYNC_ERROR | Error in Start of High-Speed transmission leader sequence |

| DXGK_DSI_EOT_SYNC_ERROR | Peripheral detected incomplete bytes in High-Speed transmission |

| DXGK_DSI_ESCAPE_MODE_ENTRY_COMMAND_ERROR | Error or peripheral does not recognize escape sequence |

| DXGK_DSI_LOW_POWER_TRANSMIT_SYNC_ERROR | Peripheral detected incomplete bytes in Low-Speed transmission |

| DXGK_DSI_FALSE_CONTROL_ERROR | Peripheral detected error in escape sequence or turnaround sequence |

| DXGK_DSI_CONTENTION_DETECTED | Contention detected |

| DXGK_DSI_CHECKSUM_ERROR_CORRECTED | A checksum error was detected and corrected |

| DXGK_DSI_CHECKSUM_ERROR_NOT_CORRECTED | A checksum error was detected but could not be corrected |

| DXGK_DSI_LONG_PACKET_PAYLOAD_CHECKSUM_ERROR | The payload checksum was incorrect for a long packet |

| DXGK_DSI_DSI_DATA_TYPE_NOT_RECOGNIZED | Peripheral does not recognize the data type sent to it |

| DXGK_DSI_DSI_VC_ID_INVALID | Peripheral was sent a command for a virtual channel which it does not support |

| DXGK_DSI_INVALID_TRANSMISSION_LENGTH | Peripheral detected that number of bytes transmitted does not match what was specified in the header |

| DXGK_DSI_DSI_PROTOCOL_VIOLATION | Peripheral detected lack of EoTP on a transmission or host failed to signal bus turn-around for a read |

### -field ResetFailed

If set, the reset did not result in the panel returning to a working state.

### -field NeedModeSet

If set on return from calling the graphics driver, the OS must perform an unoptimized mode set to the device in order to complete the reset.

### -field Results

## -remarks

## -see-also

[**IOCTL_MIPI_DSI_QUERY_CAPS](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_query_caps.md)

[**IOCTL_MIPI_DSI_RESET**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_reset.md)

[**IOCTL_MIPI_DSI_TRANSMISSION**](..\ntddvdeo\ni-ntddvdeo-ioctl_mipi_dsi_transmission.md)

