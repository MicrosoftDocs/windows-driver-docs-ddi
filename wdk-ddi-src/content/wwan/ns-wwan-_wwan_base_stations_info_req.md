---
UID: NS:wwan._WWAN_BASE_STATIONS_INFO_REQ
title: _WWAN_BASE_STATIONS_INFO_REQ (wwan.h)
description: The WWAN_BASE_STATIONS_INFO_REQ structure represents the aspects of cellular base stations information that are requested in a base stations information query.
old-location: netvista\wwan_base_stations_info_req.htm
tech.root: netvista
ms.assetid: 1948F98B-1F0B-4EB3-A2FF-01DA159B5EEB
ms.date: 05/02/2018
ms.keywords: "*PWWAN_BASE_STATIONS_INFO_REQ, PWWAN_BASE_STATIONS_INFO_REQ, PWWAN_BASE_STATIONS_INFO_REQ structure pointer [Network Drivers Starting with Windows Vista], WWAN_BASE_STATIONS_INFO_REQ, WWAN_BASE_STATIONS_INFO_REQ structure [Network Drivers Starting with Windows Vista], _WWAN_BASE_STATIONS_INFO_REQ, netvista.wwan_base_stations_info_req, wwan/PWWAN_BASE_STATIONS_INFO_REQ, wwan/WWAN_BASE_STATIONS_INFO_REQ"
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
- WWAN_BASE_STATIONS_INFO_REQ
product:
- Windows
targetos: Windows
req.typenames: WWAN_BASE_STATIONS_INFO_REQ, *PWWAN_BASE_STATIONS_INFO_REQ
---

# _WWAN_BASE_STATIONS_INFO_REQ structure


## -description


The <b>WWAN_BASE_STATIONS_INFO_REQ</b> structure represents the aspects of cellular base stations information that are requested in a base stations information query.


## -struct-fields




### -field MaxGSMCount

The maximum number of entries of GSM neighboring cells returned in the GSM network measurement reports of <a href="https://msdn.microsoft.com/ADEEB57F-79FF-4AA7-84AF-FED413E47057">WWAN_GSM_NMR</a>.


### -field MaxUMTSCount

The maximum number of entries of UMTS neighboring cells returned in the UMTS measured results list in <a href="https://msdn.microsoft.com/B62F63EB-747A-4672-9A79-5065A8BC04D1">WWAN_UMTS_MRL</a>.


### -field MaxTDSCDMACount

The maximum number of entries of TDSCDMA neighboring cells returned in the TDSCDMA measured results list in <a href="https://msdn.microsoft.com/D919EF5E-502C-4983-AFC5-F3F6E6CC8C3B">WWAN_TDSCDMA_MRL</a>.


### -field MaxLTECount

The maximum number of entries of LTE neighboring cells returned in the LTE measured results list in <a href="https://msdn.microsoft.com/5959B7A7-147D-4F20-82CC-EC1DEAAE3494">WWAN_LTE_MRL</a>.


### -field MaxCDMACount

The maximum number of entries of CDMA cells returned in the CDMA measured results list in <a href="https://msdn.microsoft.com/A19B98B5-F2E5-4AF9-9D2B-A7DD47441656">WWAN_CDMA_MRL</a>. This list includes both serving and neighboring cells.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/4327021B-93FB-4605-B7D1-A7A6D661C8DF">NDIS_WWAN_BASE_STATIONS_INFO_REQ</a>



<a href="https://msdn.microsoft.com/A19B98B5-F2E5-4AF9-9D2B-A7DD47441656">WWAN_CDMA_MRL</a>



<a href="https://msdn.microsoft.com/ADEEB57F-79FF-4AA7-84AF-FED413E47057">WWAN_GSM_NMR</a>



<a href="https://msdn.microsoft.com/5959B7A7-147D-4F20-82CC-EC1DEAAE3494">WWAN_LTE_MRL</a>



<a href="https://msdn.microsoft.com/D919EF5E-502C-4983-AFC5-F3F6E6CC8C3B">WWAN_TDSCDMA_MRL</a>



<a href="https://msdn.microsoft.com/B62F63EB-747A-4672-9A79-5065A8BC04D1">WWAN_UMTS_MRL</a>
 

 

