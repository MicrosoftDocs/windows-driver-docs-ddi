---
UID: NS:wwan._WWAN_UMTS_MRL_INFO
title: _WWAN_UMTS_MRL_INFO (wwan.h)
description: The WWAN_UMTS_MRL_INFO structure represents information about a neighboring UMTS cell.
old-location: netvista\wwan_umts_mrl_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_UMTS_MRL_INFO structure"]
ms.keywords: "*PWWAN_UMTS_MRL_INFO, PWWAN_UMTS_MRL_INFO, PWWAN_UMTS_MRL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_UMTS_MRL_INFO, WWAN_UMTS_MRL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_UMTS_MRL_INFO, netvista.wwan_umts_mrl_info, wwan/PWWAN_UMTS_MRL_INFO, wwan/WWAN_UMTS_MRL_INFO"
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
targetos: Windows
req.typenames: WWAN_UMTS_MRL_INFO, *PWWAN_UMTS_MRL_INFO
f1_keywords:
 - _WWAN_UMTS_MRL_INFO
 - wwan/_WWAN_UMTS_MRL_INFO
 - PWWAN_UMTS_MRL_INFO
 - wwan/PWWAN_UMTS_MRL_INFO
 - WWAN_UMTS_MRL_INFO
 - wwan/WWAN_UMTS_MRL_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_UMTS_MRL_INFO
---

# _WWAN_UMTS_MRL_INFO structure


## -description

The <b>WWAN_UMTS_MRL_INFO</b> structure represents information about a neighboring UMTS cell.

## -struct-fields

### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.

### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.

### -field LocationAreaCode

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.

### -field CellId

The Cell ID (0-268435455). Use 0xFFFFFFFF when this information is not available.

### -field UARFCN

The UTRA Absolute Radio Frequency Channel Number for the serving cell (0-16383). Use 0xFFFFFFFF when this information is not available.

### -field PrimaryScramblingCode

The Primary Scrambling Code of the serving cell (0-511). Use 0xFFFFFFFF when this information is not available.

### -field RSCP

The Received Signal Code Power of the serving cell. The range is -120 to -25, in units of 1dBm. Use 0xFFFFFFFF when this information is not available.

### -field ECNO

The signal to noise ratio of the serving cell; the ratio of the received energy per PN chip for the CPICH to the total received. The range is -50 to 0, in units of 1dBm. Use 1 when this information is not available.

### -field PathLoss

The path loss of the serving cell (46-173). Use 0xFFFFFFFF when this information is not available.

### -field Data

The data buffer containing <i>ProviderId</i>.

## -see-also

<a href="/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_mrl">WWAN_UMTS_MRL</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_serving_cell_info">WWAN_UMTS_SERVING_CELL_INFO</a>
