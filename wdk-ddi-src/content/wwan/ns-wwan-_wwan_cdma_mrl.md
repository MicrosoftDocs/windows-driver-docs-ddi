---
UID: NS:wwan._WWAN_CDMA_MRL
title: _WWAN_CDMA_MRL (wwan.h)
description: The WWAN_CDMA_MRL structure represents the measured results list (MRL) of both serving and neighboring CDMA cells.
old-location: netvista\wwan_cdma_mrl.htm
tech.root: netvista
ms.date: 03/11/2022
keywords: ["WWAN_CDMA_MRL structure"]
ms.keywords: "*PWWAN_CDMA_MRL, PWWAN_CDMA_MRL, PWWAN_CDMA_MRL structure pointer [Network Drivers Starting with Windows Vista], WWAN_CDMA_MRL, WWAN_CDMA_MRL structure [Network Drivers Starting with Windows Vista], _WWAN_CDMA_MRL, netvista.wwan_cdma_mrl, wwan/PWWAN_CDMA_MRL, wwan/WWAN_CDMA_MRL"
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
req.typenames: WWAN_CDMA_MRL, *PWWAN_CDMA_MRL
f1_keywords:
 - _WWAN_CDMA_MRL
 - wwan/_WWAN_CDMA_MRL
 - PWWAN_CDMA_MRL
 - wwan/PWWAN_CDMA_MRL
 - WWAN_CDMA_MRL
 - wwan/WWAN_CDMA_MRL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_CDMA_MRL
 - PWWAN_CDMA_MRL
 - WWAN_CDMA_MRL
---

# _WWAN_CDMA_MRL structure


## -description

The <b>WWAN_CDMA_MRL</b> structure represents the measured results list (MRL) of both serving and neighboring CDMA cells.

## -struct-fields

### -field ElementCount

The count of MRL entries following this member.

### -field CDMAMrl

The array of MRL records, each specified as a <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl_info">WWAN_CDMA_MRL_INFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl_info">WWAN_CDMA_MRL_INFO</a>

