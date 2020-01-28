---
UID: NS:wwan._WWAN_CDMA_MRL
title: _WWAN_CDMA_MRL (wwan.h)
description: The WWAN_CDMA_MRL structure represents the measured results list (MRL) of both serving and neighboring CDMA cells.
old-location: netvista\wwan_cdma_mrl.htm
tech.root: netvista
ms.assetid: A19B98B5-F2E5-4AF9-9D2B-A7DD47441656
ms.date: 05/02/2018
ms.keywords: "*PWWAN_CDMA_MRL, PWWAN_CDMA_MRL, PWWAN_CDMA_MRL structure pointer [Network Drivers Starting with Windows Vista], WWAN_CDMA_MRL, WWAN_CDMA_MRL structure [Network Drivers Starting with Windows Vista], _WWAN_CDMA_MRL, netvista.wwan_cdma_mrl, wwan/PWWAN_CDMA_MRL, wwan/WWAN_CDMA_MRL"
f1_keywords:
 - "wwan/WWAN_CDMA_MRL"
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
- WWAN_CDMA_MRL
product:
- Windows
targetos: Windows
req.typenames: WWAN_CDMA_MRL, *PWWAN_CDMA_MRL
---

# _WWAN_CDMA_MRL structure


## -description


The <b>WWAN_CDMA_MRL</b> structure represents the measured results list (MRL) of both serving and neighboring CDMA cells.


## -struct-fields




### -field ElementCount

The count of MRL entries following this member.


### -field CDMAMrl

 




#### - CDMAMrl[ANYSIZE_ARRAY]

The array of MRL records, each specified as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl_info">WWAN_CDMA_MRL_INFO</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_cdma_mrl_info">WWAN_CDMA_MRL_INFO</a>
 

 

