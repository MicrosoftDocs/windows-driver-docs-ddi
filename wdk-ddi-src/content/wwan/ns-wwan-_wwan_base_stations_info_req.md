---
UID: NS:wwan._WWAN_BASE_STATIONS_INFO_REQ
title: "_WWAN_BASE_STATIONS_INFO_REQ"
author: windows-driver-content
description: The WWAN_BASE_STATIONS_INFO_REQ structure represents the aspects of cellular base stations information that are requested in a base stations information query.
old-location: netvista\wwan_base_stations_info_req.htm
old-project: netvista
ms.assetid: 1948F98B-1F0B-4EB3-A2FF-01DA159B5EEB
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_WWAN_BASE_STATIONS_INFO_REQ, WWAN_BASE_STATIONS_INFO_REQ, netvista.wwan_base_stations_info_req, PWWAN_BASE_STATIONS_INFO_REQ structure pointer [Network Drivers Starting with Windows Vista], *PWWAN_BASE_STATIONS_INFO_REQ, PWWAN_BASE_STATIONS_INFO_REQ, WWAN_BASE_STATIONS_INFO_REQ structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_BASE_STATIONS_INFO_REQ, wwan/WWAN_BASE_STATIONS_INFO_REQ"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_BASE_STATIONS_INFO_REQ
product: Windows
targetos: Windows
req.typenames: WWAN_BASE_STATIONS_INFO_REQ, *PWWAN_BASE_STATIONS_INFO_REQ
req.product: Windows 10 or later.
---

# _WWAN_BASE_STATIONS_INFO_REQ structure


## -description


The <b>WWAN_BASE_STATIONS_INFO_REQ</b> structure represents the aspects of cellular base stations information that are requested in a base stations information query.


## -syntax


````
typedef struct _WWAN_BASE_STATIONS_INFO_REQ {
  ULONG MaxGSMCount;
  ULONG MaxUMTSCount;
  ULONG MaxTDSCDMACount;
  ULONG MaxLTECount;
  ULONG MaxCDMACount;
} WWAN_BASE_STATIONS_INFO_REQ, *PWWAN_BASE_STATIONS_INFO_REQ;
````


## -struct-fields




#### - MaxGSMCount

The maximum number of entries of GSM neighboring cells returned in the GSM network measurement reports of <a href="..\wwan\ns-wwan-_wwan_gsm_nmr.md">WWAN_GSM_NMR</a>.


#### - MaxUMTSCount

The maximum number of entries of UMTS neighboring cells returned in the UMTS measured results list in <a href="..\wwan\ns-wwan-_wwan_umts_mrl.md">WWAN_UMTS_MRL</a>.


#### - MaxTDSCDMACount

The maximum number of entries of TDSCDMA neighboring cells returned in the TDSCDMA measured results list in <a href="..\wwan\ns-wwan-_wwan_tdscdma_mrl.md">WWAN_TDSCDMA_MRL</a>.


#### - MaxLTECount

The maximum number of entries of LTE neighboring cells returned in the LTE measured results list in <a href="..\wwan\ns-wwan-_wwan_lte_mrl.md">WWAN_LTE_MRL</a>.


#### - MaxCDMACount

The maximum number of entries of CDMA cells returned in the CDMA measured results list in <a href="..\wwan\ns-wwan-_wwan_cdma_mrl.md">WWAN_CDMA_MRL</a>. This list includes both serving and neighboring cells.


## -see-also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_base_stations_info_req.md">NDIS_WWAN_BASE_STATIONS_INFO_REQ</a>

<a href="..\wwan\ns-wwan-_wwan_lte_mrl.md">WWAN_LTE_MRL</a>

<a href="..\wwan\ns-wwan-_wwan_umts_mrl.md">WWAN_UMTS_MRL</a>

<a href="..\wwan\ns-wwan-_wwan_cdma_mrl.md">WWAN_CDMA_MRL</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>

<a href="..\wwan\ns-wwan-_wwan_tdscdma_mrl.md">WWAN_TDSCDMA_MRL</a>

<a href="..\wwan\ns-wwan-_wwan_gsm_nmr.md">WWAN_GSM_NMR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_BASE_STATIONS_INFO_REQ structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

