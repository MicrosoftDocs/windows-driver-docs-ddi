---
UID: NS:wwan._WWAN_GSM_SERVING_CELL_INFO
title: _WWAN_GSM_SERVING_CELL_INFO (wwan.h)
description: The WWAN_GSM_SERVING_CELL_INFO structure represents information about the GSM serving cell.
old-location: netvista\wwan_gsm_serving_cell_info.htm
tech.root: netvista
ms.assetid: 37F6BD26-55F3-4E46-9C39-97A95B6FF5B1
ms.date: 05/02/2018
ms.keywords: "*PWWAN_GSM_SERVING_CELL_INFO, PWWAN_GSM_SERVING_CELL_INFO, PWWAN_GSM_SERVING_CELL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_GSM_SERVING_CELL_INFO, WWAN_GSM_SERVING_CELL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_GSM_SERVING_CELL_INFO, netvista.wwan_gsm_serving_cell_info, wwan/PWWAN_GSM_SERVING_CELL_INFO, wwan/WWAN_GSM_SERVING_CELL_INFO"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
- wwan.h
api_name:
- WWAN_GSM_SERVING_CELL_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_GSM_SERVING_CELL_INFO, *PWWAN_GSM_SERVING_CELL_INFO
---

# _WWAN_GSM_SERVING_CELL_INFO structure

## -description

The **WWAN_GSM_SERVING_CELL_INFO** structure represents information about the GSM serving cell.

## -struct-fields

### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called *ProviderId* that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no *ProviderId* information is returned.

### -field ProviderIdSize

The size, in bytes, used for *ProviderId*.

### -field LocationAreaCode

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.

### -field CellId

The Cell ID (0-65535). Use 0xFFFFFFFF when this information is not available.

### -field TimingAdvance

The Timing Advance (0-255) in bit periods, where a bit period is 48/13µs. Use 0xFFFFFFFF when this information is not available.

### -field ARFCN

The Absolute Radio Frequency Channel Number of the serving cell (0-1023). Use 0xFFFFFFFF when this information is not available.

### -field BaseStationId

The Base Station ID - the base station color code and the network identity code. Use 0xFFFFFFFF when this information is not available.

### -field RxLevel

The received signal strength (RSS) of the serving cell (0-63), where

`X = 0, if RSS < -110 dBm`

`X = 63, if RSS > -47 dBm`

`X = integer [RSS + 110], if -110 <= RSS <= -47`

Use 0xFFFFFFFF when this information is not available.

### -field Data

The data buffer containing *ProviderId*.

## -see-also

[MB base stations information query support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support)

[WWAN_BASE_STATIONS_INFO](ns-wwan-_wwan_base_stations_info.md)

[WWAN_GSM_NMR](ns-wwan-_wwan_gsm_nmr.md)

[WWAN_GSM_NMR_INFO](ns-wwan-_wwan_gsm_nmr_info.md)
