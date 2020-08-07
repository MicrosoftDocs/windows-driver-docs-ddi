---
UID: NS:wwan._WWAN_BASE_STATIONS_INFO_REQ
title: _WWAN_BASE_STATIONS_INFO_REQ (wwan.h)
description: The WWAN_BASE_STATIONS_INFO_REQ structure represents the aspects of cellular base stations information that are requested in a base stations information query.
old-location: netvista\wwan_base_stations_info_req.htm
tech.root: netvista
ms.assetid: 1948F98B-1F0B-4EB3-A2FF-01DA159B5EEB
ms.date: 05/02/2018
keywords: ["WWAN_BASE_STATIONS_INFO_REQ structure"]
ms.keywords: "*PWWAN_BASE_STATIONS_INFO_REQ, PWWAN_BASE_STATIONS_INFO_REQ, PWWAN_BASE_STATIONS_INFO_REQ structure pointer [Network Drivers Starting with Windows Vista], WWAN_BASE_STATIONS_INFO_REQ, WWAN_BASE_STATIONS_INFO_REQ structure [Network Drivers Starting with Windows Vista], _WWAN_BASE_STATIONS_INFO_REQ, netvista.wwan_base_stations_info_req, wwan/PWWAN_BASE_STATIONS_INFO_REQ, wwan/WWAN_BASE_STATIONS_INFO_REQ"
f1_keywords:
 - "wwan/WWAN_BASE_STATIONS_INFO_REQ"
 - "WWAN_BASE_STATIONS_INFO_REQ"
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
- WWAN_BASE_STATIONS_INFO_REQ
targetos: Windows
req.typenames: WWAN_BASE_STATIONS_INFO_REQ, *PWWAN_BASE_STATIONS_INFO_REQ
---

# _WWAN_BASE_STATIONS_INFO_REQ structure


## -description


The <b>WWAN_BASE_STATIONS_INFO_REQ</b> structure represents the aspects of cellular base stations information that are requested in a base stations information query.


## -struct-fields




### -field MaxGSMCount

The maximum number of entries of GSM neighboring cells returned in the GSM network measurement reports of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_nmr">WWAN_GSM_NMR</a>.


### -field MaxUMTSCount

The maximum number of entries of UMTS neighboring cells returned in the UMTS measured results list in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_mrl">WWAN_UMTS_MRL</a>.


### -field MaxTDSCDMACount

The maximum number of entries of TDSCDMA neighboring cells returned in the TDSCDMA measured results list in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>.


### -field MaxLTECount

The maximum number of entries of LTE neighboring cells returned in the LTE measured results list in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_mrl">WWAN_LTE_MRL</a>.


### -field MaxCDMACount

The maximum number of entries of CDMA cells returned in the CDMA measured results list in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl">WWAN_CDMA_MRL</a>. This list includes both serving and neighboring cells.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_base_stations_info_req">NDIS_WWAN_BASE_STATIONS_INFO_REQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl">WWAN_CDMA_MRL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_nmr">WWAN_GSM_NMR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_lte_mrl">WWAN_LTE_MRL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_umts_mrl">WWAN_UMTS_MRL</a>
 

 

