---
UID: NS:ndiswwan._NDIS_WWAN_QUERY_READY_INFO
tech.root: netvista
title: NDIS_WWAN_QUERY_READY_INFO
ms.date: 02/22/2022
targetos: Windows
description: The NDIS_WWAN_QUERY_READY_INFO structure represents a SIM slot ID for OID_WWAN_READY_INFO query requests.
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
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_QUERY_READY_INFO, *PNDIS_WWAN_QUERY_READY_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_QUERY_READY_INFO
 - PNDIS_WWAN_QUERY_READY_INFO
 - NDIS_WWAN_QUERY_READY_INFO
f1_keywords:
 - _NDIS_WWAN_QUERY_READY_INFO
 - ndiswwan/_NDIS_WWAN_QUERY_READY_INFO
 - PNDIS_WWAN_QUERY_READY_INFO
 - ndiswwan/PNDIS_WWAN_QUERY_READY_INFO
 - NDIS_WWAN_QUERY_READY_INFO
 - ndiswwan/NDIS_WWAN_QUERY_READY_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_WWAN_QUERY_READY_INFO
---

## -description

The **NDIS_WWAN_QUERY_READY_INFO** structure represents the SIM slot ID that is associated with an [OID_WWAN_READY_INFO](/windows-hardware/drivers/network/oid-wwan-ready-info) query request.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_QUERY_READY_INFO** structure. 

|Header submember|Value|
|---|---|
|Type|NDIS_OBJECT_TYPE_DEFAULT|
|Revision|NDIS_WWAN_GENERAL_REVISION_1|
|Size|sizeof(NDIS_WWAN_QUERY_READY_INFO)|

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header).

### -field QueryReadyInfo

A [**WWAN_QUERY_READY_INFO**](../wwan/ns-wwan-wwan_query_ready_info.md) structure that represents the slot ID.

## -remarks

## -see-also

[**WWAN_QUERY_READY_INFO**](../wwan/ns-wwan-wwan_query_ready_info.md)

[OID_WWAN_READY_INFO](/windows-hardware/drivers/network/oid-wwan-ready-info)