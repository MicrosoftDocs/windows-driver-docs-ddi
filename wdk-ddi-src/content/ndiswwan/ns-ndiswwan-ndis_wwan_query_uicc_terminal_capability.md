---
UID: NS:ndiswwan._NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
tech.root: netvista
title: NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
ms.date: 03/10/2022
targetos: Windows
description: The NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY structure represents the SIM slot ID that is associated with an OID_WWAN_UICC_TERMINAL_CAPABILITY query request.
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
req.typenames: NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY, *PNDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - PNDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
f1_keywords:
 - _NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - ndiswwan/_NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - PNDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - ndiswwan/PNDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
 - ndiswwan/NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY
---

## -description

The **NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY** structure represents the SIM slot ID that is associated with an [OID_WWAN_UICC_TERMINAL_CAPABILITY](/windows-hardware/drivers/network/oid-wwan-uicc-terminal-capability) query request.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY** structure. 

|Header submember|Value|
|---|---|
|Type|NDIS_OBJECT_TYPE_DEFAULT|
|Revision|NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY_REVISION_1|
|Size|sizeof(NDIS_WWAN_QUERY_UICC_TERMINAL_CAPABILITY)|

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md).


### -field QueryUiccTerminalCapability

A [**WWAN_QUERY_UICC_TERMINAL_CAPABILITY**](../wwan/ns-wwan-wwan_query_uicc_terminal_capability.md) structure that represents the slot ID.


## -remarks

## -see-also

[OID_WWAN_UICC_TERMINAL_CAPABILITY](/windows-hardware/drivers/network/oid-wwan-uicc-terminal-capability)

[**WWAN_QUERY_UICC_TERMINAL_CAPABILITY**](../wwan/ns-wwan-wwan_query_uicc_terminal_capability.md)