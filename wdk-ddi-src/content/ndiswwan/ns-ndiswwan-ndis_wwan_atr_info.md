---
UID: NS:ndiswwan._NDIS_WWAN_ATR_INFO
tech.root: netvista
title: NDIS_WWAN_ATR_INFO
ms.date: 02/23/2022
targetos: Windows
description: The NDIS_WWAN_ATR_INFO structure represents a SIM card's Answer to Reset (ATR) information.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndiswwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_ATR_INFO, *PNDIS_WWAN_ATR_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_ATR_INFO
 - PNDIS_WWAN_ATR_INFO
 - NDIS_WWAN_ATR_INFO
f1_keywords:
 - _NDIS_WWAN_ATR_INFO
 - ndiswwan/_NDIS_WWAN_ATR_INFO
 - PNDIS_WWAN_ATR_INFO
 - ndiswwan/PNDIS_WWAN_ATR_INFO
 - NDIS_WWAN_ATR_INFO
 - ndiswwan/NDIS_WWAN_ATR_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_WWAN_ATR_INFO
---

## -description

The **NDIS_WWAN_ATR_INFO** structure represents a SIM card's Answer to Reset (ATR) information.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_ATR_INFO** structure.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_ATR_INFO_REVISION_1 |
| Size | sizeof(NDIS_WWAN_ATR_INFO) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md).

### -field uStatus

A **WWAN_STATUS** value that indicates the result of the query request.

### -field AtrInfo

A [**WWAN_ATR_INFO**](../wwan/ns-wwan-wwan_atr_info.md) structure that represents the ATR information. 

## -remarks

## -see-also

[**WWAN_ATR_INFO**](../wwan/ns-wwan-wwan_atr_info.md)

[OID_WWAN_UICC_ATR](/windows-hardware/drivers/network/oid-wwan-uicc-atr)

[NDIS_STATUS_WWAN_ATR_INFO](/windows-hardware/drivers/network/ndis-status-wwan-atr-info)