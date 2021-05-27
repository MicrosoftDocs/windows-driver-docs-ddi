---
UID: NS:wwan._WWAN_BASE_STATIONS_INFO
title: _WWAN_BASE_STATIONS_INFO (wwan.h)
description: The WWAN_BASE_STATIONS_INFO structure represents information about both serving and neighboring base stations.
old-location: netvista\wwan_base_stations_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_BASE_STATIONS_INFO structure"]
ms.keywords: "*PWWAN_BASE_STATIONS_INFO, PWWAN_BASE_STATIONS_INFO, PWWAN_BASE_STATIONS_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_BASE_STATIONS_INFO, WWAN_BASE_STATIONS_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_BASE_STATIONS_INFO, netvista.wwan_base_stations_info, wwan/PWWAN_BASE_STATIONS_INFO, wwan/WWAN_BASE_STATIONS_INFO"
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
req.typenames: WWAN_BASE_STATIONS_INFO, *PWWAN_BASE_STATIONS_INFO
f1_keywords:
 - _WWAN_BASE_STATIONS_INFO
 - wwan/_WWAN_BASE_STATIONS_INFO
 - PWWAN_BASE_STATIONS_INFO
 - wwan/PWWAN_BASE_STATIONS_INFO
 - WWAN_BASE_STATIONS_INFO
 - wwan/WWAN_BASE_STATIONS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_BASE_STATIONS_INFO
 - PWWAN_BASE_STATIONS_INFO
 - WWAN_BASE_STATIONS_INFO
---

# _WWAN_BASE_STATIONS_INFO structure


## -description

The <b>WWAN_BASE_STATIONS_INFO</b> structure represents information about both serving and neighboring base stations.

## -struct-fields

### -field SystemType

Indicates the system type (or types) for which serving cell information is valid. This member is a bitmask of one or more system types as defined in the <b>WwanDataClass</b> member of <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>.

### -field SystemSubType

Indicates the 5G data subclass for which serving cell information is valid. This member is a bitmask of one or more system subtypes as defined in the <b>dataSubclass</b> member of <a href="/windows-hardware/drivers/ddi/wwan/nf-wwan-is_5g_5gc_present">IS_5G_5GC_PRESENT</a>. This member is only valid when the **SystemType** field above indicates that 5G serving cell information is valid. Otherwise, this value should be **WWAN_DATA_SUBCLASS_NONE**.

### -field GSMServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the GSM serving cell information. This member can be NULL when the technology of the serving cell is not GSM.

### -field GSMServingCellSize

The size, in bytes, used for the buffer containing the GSM serving cell info, which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_serving_cell_info">WWAN_GSM_SERVING_CELL_INFO</a>.

### -field UMTSServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the UMTS serving cell information. This member can be NULL when the technology of serving cell is not UMTS.

### -field UMTSServingCellSize

The size, in bytes, used for the buffer containing the UMTS serving cell info, which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_serving_cell_info">WWAN_UMTS_SERVING_CELL_INFO</a>.

### -field TDSCDMAServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the TDSCDMA serving cell information. This member can be NULL when the technology of serving cell is not TDSCDMA.

### -field TDSCDMAServingCellSize

The size, in bytes, used for the buffer containing the TDSCDMA serving cell info, which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_serving_cell_info">WWAN_TDSCDMA_SERVING_CELL_INFO</a>.

### -field LTEServingCellOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the LTE serving cell information. This member can be NULL when the technology of serving cell is not LTE.

### -field LTEServingCellSize

The size, in bytes, used for the buffer containing the LTE serving cell info, which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_serving_cell_info">WWAN_LTE_SERVING_CELL_INFO</a>.

### -field GSMNmrOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the GSM network measurement report. This member can be NULL when no GSM neighboring network is returned in the measurement report.

### -field GSMNmrSize

The size, in bytes, of the buffer containing the GSM network measurement report (NMR), which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_nmr">WWAN_GSM_NMR</a>.

### -field UMTSMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing UMTS measured results list. This member can be NULL when no UMTS neighboring network is returned in the measurement report.

### -field UMTSMrlSize

The size, in bytes, of the buffer containing the UMTS measured results list (MRL), which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_mrl">WWAN_UMTS_MRL</a>.

### -field TDSCDMAMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing TDSCDMA measured results list. This member can be NULL when no TDSCDMA neighboring network is returned in the measurement report.

### -field TDSCDMAMrlSize

The size, in bytes, of the buffer containing the TDSCDMA measured results list (MRL), which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>.

### -field LTEMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing LTE measured results list. This member can be NULL when no LTE neighboring network is returned in the measurement report.

### -field LTEMrlSize

The size, in bytes, of the buffer containing the LTE measured results list (MRL), which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_mrl">WWAN_LTE_MRL</a>.

### -field CDMAMrlOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing CDMA measured results list. This member can be NULL when no CDMA neighboring network is returned in the measurement report.

### -field CDMAMrlSize

The size, in bytes, of the buffer containing the CDMA measured results list (MRL), which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl">WWAN_CDMA_MRL</a>.


### -field NRServingCellsOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the NR measure results list. This member can be NULL when no NR serving cells are available for devices without 5G capability.

### -field NRServingCellsSize

The size, in bytes, of the buffer containing the 5G NR measured results, which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-wwan_nr_serving_cells">WWAN_NR_SERVING_CELLS</a>.

### -field NRNeighborCellsOffset

The offset in bytes, calculated from the beginning of this structure, to the buffer containing the NR neighbor cells measurement results. This member can be NULL when no NR neighbor cells are available.

### -field NRNeighborCellsSize

The size, in bytes, of the buffer containing the NR measured results, which is formatted as <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-wwan_nr_neighbor_cells">WWAN_NR_NEIGHBOR_CELLS</a>.

### -field BaseStationsData

[ANYSIZE_ARRAY] The data buffer containing the base stations information. This buffer is where the structures specified by the other members of <b>WWAN_BASE_STATIONS_INFO</b> reside.

## -see-also

<a href="/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_base_stations_info">NDIS_WWAN_BASE_STATIONS_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl">WWAN_CDMA_MRL</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_nmr">WWAN_GSM_NMR</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_serving_cell_info">WWAN_GSM_SERVING_CELL_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_mrl">WWAN_LTE_MRL</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_serving_cell_info">WWAN_LTE_SERVING_CELL_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_serving_cell_info">WWAN_TDSCDMA_SERVING_CELL_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_mrl">WWAN_UMTS_MRL</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_serving_cell_info">WWAN_UMTS_SERVING_CELL_INFO</a>

