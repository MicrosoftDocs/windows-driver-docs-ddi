---
UID: NS:wwan._WWAN_QUERY_ATR_INFO
tech.root: netvista
title: WWAN_QUERY_ATR_INFO
ms.date: 02/25/2022
targetos: Windows
description: The WWAN_QUERY_ATR_INFO structure represents the SIM slot ID that is associated with an OID_WWAN_UICC_ATR query request.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_QUERY_ATR_INFO, *PWWAN_QUERY_ATR_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_QUERY_ATR_INFO
 - PWWAN_QUERY_ATR_INFO
 - WWAN_QUERY_ATR_INFO
f1_keywords:
 - _WWAN_QUERY_ATR_INFO
 - wwan/_WWAN_QUERY_ATR_INFO
 - PWWAN_QUERY_ATR_INFO
 - wwan/PWWAN_QUERY_ATR_INFO
 - WWAN_QUERY_ATR_INFO
 - wwan/WWAN_QUERY_ATR_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_QUERY_ATR_INFO
---

## -description

The **WWAN_QUERY_ATR_INFO** structure represents the SIM slot ID that is associated with an [OID_WWAN_UICC_ATR](/windows-hardware/drivers/network/oid-wwan-uicc-atr) query request.

## -struct-fields

### -field SlotId

A ULONG value that specifies the intended SIM slot of the operation. For a single SIM device, this value is 0. For a dual SIM device, this value is [0..1].

## -remarks

## -see-also

[**NDIS_WWAN_QUERY_ATR_INFO**](../ndiswwan/ns-ndiswwan-ndis_wwan_query_atr_info.md)

[OID_WWAN_UICC_ATR](/windows-hardware/drivers/network/oid-wwan-uicc-atr)
