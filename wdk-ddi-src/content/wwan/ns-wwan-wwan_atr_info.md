---
UID: NS:wwan._WWAN_ATR_INFO
tech.root: netvista
title: WWAN_ATR_INFO
ms.date: 02/18/2022
targetos: Windows
description: The WWAN_ATR_INFO structure represents a SIM card's Answer to Reset (ATR) information.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_ATR_INFO, *PWWAN_ATR_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_ATR_INFO
 - PWWAN_ATR_INFO
 - WWAN_ATR_INFO
f1_keywords:
 - _WWAN_ATR_INFO
 - wwan/_WWAN_ATR_INFO
 - PWWAN_ATR_INFO
 - wwan/PWWAN_ATR_INFO
 - WWAN_ATR_INFO
 - wwan/WWAN_ATR_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_ATR_INFO
---

## -description

The **WWAN_ATR_INFO** structure represents a SIM card's Answer to Reset (ATR) information.

## -struct-fields

### -field AtrLength

The length of the ATR data.

### -field Atr

A byte array representing the ATR data.

## -remarks

## -see-also

[**NDIS_WWAN_ATR_INFO**](../ndiswwan/ns-ndiswwan-ndis_wwan_atr_info.md)

[OID_WWAN_UICC_ATR](/windows-hardware/drivers/network/oid-wwan-uicc-atr)

[NDIS_STATUS_WWAN_ATR_INFO](/windows-hardware/drivers/network/ndis-status-wwan-atr-info)