---
UID: NS:ndiswwan._NDIS_WWAN_QUERY_UICC_RESET
tech.root: netvista
title: NDIS_WWAN_QUERY_UICC_RESET
ms.date: 03/10/2022
targetos: Windows
description: The NDIS_WWAN_QUERY_UICC_RESET structure represents the SIM slot ID that is associated with an OID_WWAN_UICC_RESET query request.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndiswwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_QUERY_UICC_RESET, *PNDIS_WWAN_QUERY_UICC_RESET
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_QUERY_UICC_RESET
 - PNDIS_WWAN_QUERY_UICC_RESET
 - NDIS_WWAN_QUERY_UICC_RESET
f1_keywords:
 - _NDIS_WWAN_QUERY_UICC_RESET
 - ndiswwan/_NDIS_WWAN_QUERY_UICC_RESET
 - PNDIS_WWAN_QUERY_UICC_RESET
 - ndiswwan/PNDIS_WWAN_QUERY_UICC_RESET
 - NDIS_WWAN_QUERY_UICC_RESET
 - ndiswwan/NDIS_WWAN_QUERY_UICC_RESET
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_WWAN_QUERY_UICC_RESET
---

## -description

The **NDIS_WWAN_QUERY_UICC_RESET** structure represents the SIM slot ID that is associated with an [OID_WWAN_UICC_RESET](/windows-hardware/drivers/network/oid-wwan-uicc-reset) query request.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_QUERY_UICC_RESET** structure. 

|Header submember|Value|
|---|---|
|Type|NDIS_OBJECT_TYPE_DEFAULT|
|Revision|NDIS_WWAN_QUERY_UICC_RESET_REVISION_1|
|Size|sizeof(NDIS_WWAN_QUERY_UICC_RESET)|

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md).

### -field QueryUiccReset

A [**WWAN_QUERY_UICC_RESET**](../wwan/ns-wwan-wwan_query_uicc_reset.md) structure that represents the slot ID.

## -remarks

## -see-also

[OID_WWAN_UICC_RESET](/windows-hardware/drivers/network/oid-wwan-uicc-reset)

[**WWAN_QUERY_UICC_RESET**](../wwan/ns-wwan-wwan_query_uicc_reset.md)