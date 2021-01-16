---
UID: NS:wwan._WWAN_GSM_NMR
title: _WWAN_GSM_NMR (wwan.h)
description: The WWAN_GSM_NMR structure represents the network measurement report (NMR) of neighboring GSM cells.
old-location: netvista\wwan_gsm_nmr.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_GSM_NMR structure"]
ms.keywords: "*PWWAN_GSM_NMR, PWWAN_GSM_NMR, PWWAN_GSM_NMR structure pointer [Network Drivers Starting with Windows Vista], WWAN_GSM_NMR, WWAN_GSM_NMR structure [Network Drivers Starting with Windows Vista], _WWAN_GSM_NMR, netvista.wwan_gsm_nmr, wwan/PWWAN_GSM_NMR, wwan/WWAN_GSM_NMR"
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
req.typenames: WWAN_GSM_NMR, *PWWAN_GSM_NMR
f1_keywords:
 - _WWAN_GSM_NMR
 - wwan/_WWAN_GSM_NMR
 - PWWAN_GSM_NMR
 - wwan/PWWAN_GSM_NMR
 - WWAN_GSM_NMR
 - wwan/WWAN_GSM_NMR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_GSM_NMR
 - PWWAN_GSM_NMR
 - WWAN_GSM_NMR
---

# _WWAN_GSM_NMR structure


## -description

The <b>WWAN_GSM_NMR</b> structure represents the network measurement report (NMR) of neighboring GSM cells.

## -struct-fields

### -field ElementCount

The count of NMR entries following this member.

### -field GSMNmr

The array of NMR records, each specified as a <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_nmr_info">WWAN_GSM_NMR_INFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_nmr_info">WWAN_GSM_NMR_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_gsm_serving_cell_info">WWAN_GSM_SERVING_CELL_INFO</a>

