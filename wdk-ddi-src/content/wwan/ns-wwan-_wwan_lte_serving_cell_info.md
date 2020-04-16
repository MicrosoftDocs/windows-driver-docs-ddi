---
UID: NS:wwan._WWAN_LTE_SERVING_CELL_INFO
title: _WWAN_LTE_SERVING_CELL_INFO (wwan.h)
description: The WWAN_LTE_SERVING_CELL_INFO structure represents information about the LTE serving cell.
old-location: netvista\wwan_lte_serving_cell_info.htm
tech.root: netvista
ms.assetid: 17A78DC7-A89D-405A-983E-FC0DC469A4B0
ms.date: 05/02/2018
keywords: ["_WWAN_LTE_SERVING_CELL_INFO structure"]
ms.keywords: "*PWWAN_LTE_SERVING_CELL_INFO, PWWAN_LTE_SERVING_CELL_INFO, PWWAN_LTE_SERVING_CELL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_LTE_SERVING_CELL_INFO, WWAN_LTE_SERVING_CELL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_LTE_SERVING_CELL_INFO, netvista.wwan_lte_serving_cell_info, wwan/PWWAN_LTE_SERVING_CELL_INFO, wwan/WWAN_LTE_SERVING_CELL_INFO"
f1_keywords:
 - "wwan/WWAN_LTE_SERVING_CELL_INFO"
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
- WWAN_LTE_SERVING_CELL_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_LTE_SERVING_CELL_INFO, *PWWAN_LTE_SERVING_CELL_INFO
---

# _WWAN_LTE_SERVING_CELL_INFO structure


## -description


The <b>WWAN_LTE_SERVING_CELL_INFO</b> structure represents information about the LTE serving cell.


## -struct-fields




### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.


### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.


### -field CellId

The Cell ID (0-268435455). Use 0xFFFFFFFF when this information is not available.


### -field EARFCN

The Radio Frequency Channel Number of the serving cell (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field PhysicalCellId

The Physical Cell ID (0-503). Use 0xFFFFFFFF when this information is not available.


### -field TAC

The Tracking Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field RSRP

The Average Reference Signal Received Power. The range is -140 to -44, in units of 1dBm. Use 0xFFFFFFFF when this information is not available.


### -field RSRQ

The Average Reference Signal Received Quality. The range is -20 to -3, in units of 1dBm. Use 0xFFFFFFFF when this information is not available.


### -field TimingAdvance

The Timing Advance (0-255). Use 0xFFFFFFFF when this information is not available.


### -field Data

The data buffer containing <i>ProviderId</i>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_mrl">WWAN_LTE_MRL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_mrl_info">WWAN_LTE_MRL_INFO</a>
 

 

