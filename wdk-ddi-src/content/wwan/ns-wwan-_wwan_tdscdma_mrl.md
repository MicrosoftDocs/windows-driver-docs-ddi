---
UID: NS:wwan._WWAN_TDSCDMA_MRL
title: _WWAN_TDSCDMA_MRL (wwan.h)
description: The WWAN_TDSCDMA_MRL structure represents the measured results list (MRL) of neighboring TDSCDMA cells.
old-location: netvista\wwan_tdscdma_mrl.htm
tech.root: netvista
ms.assetid: D919EF5E-502C-4983-AFC5-F3F6E6CC8C3B
ms.date: 05/02/2018
keywords: ["WWAN_TDSCDMA_MRL structure"]
ms.keywords: "*PWWAN_TDSCDMA_MRL, PWWAN_TDSCDMA_MRL, PWWAN_TDSCDMA_MRL structure pointer [Network Drivers Starting with Windows Vista], WWAN_TDSCDMA_MRL, WWAN_TDSCDMA_MRL structure [Network Drivers Starting with Windows Vista], _WWAN_TDSCDMA_MRL, netvista.wwan_tdscdma_mrl, wwan/PWWAN_TDSCDMA_MRL, wwan/WWAN_TDSCDMA_MRL"
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
req.typenames: WWAN_TDSCDMA_MRL, *PWWAN_TDSCDMA_MRL
f1_keywords:
 - _WWAN_TDSCDMA_MRL
 - wwan/_WWAN_TDSCDMA_MRL
 - PWWAN_TDSCDMA_MRL
 - wwan/PWWAN_TDSCDMA_MRL
 - WWAN_TDSCDMA_MRL
 - wwan/WWAN_TDSCDMA_MRL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_TDSCDMA_MRL
---

# _WWAN_TDSCDMA_MRL structure


## -description

The <b>WWAN_TDSCDMA_MRL</b> structure represents the measured results list (MRL) of neighboring TDSCDMA cells.

## -struct-fields

### -field ElementCount

The count of MRL entries following this member.

### -field TDSCDMAMrl

The array of MRL records, each specified as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_mrl_info">WWAN_TDSCDMA_MRL_INFO</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_mrl_info">WWAN_TDSCDMA_MRL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_tdscdma_serving_cell_info">WWAN_TDSCDMA_SERVING_CELL_INFO</a>

