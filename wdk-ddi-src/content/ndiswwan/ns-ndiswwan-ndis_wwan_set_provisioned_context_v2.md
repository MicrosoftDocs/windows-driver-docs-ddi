---
UID: NS:ndiswwan._NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
tech.root: netvista
title: NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
ms.date: 01/19/2022
targetos: Windows
description: The NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2 structure represents the command to set the provisioned context state of the MB device.
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
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2, *PNDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - PNDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
f1_keywords:
 - _NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - ndiswwan/_NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - PNDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - ndiswwan/PNDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
 - ndiswwan/NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2
---

## -description

The **NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2** structure represents the command to set the provisioned context state of the MB device.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2 structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

|Header submember|Value|
|---|---|
|Type|NDIS_OBJECT_TYPE_DEFAULT|
|Revision|NDIS_WWAN_SET_PROVISIONED_CONTEXT_REVISION_2|
|Size|sizeof(NDIS_WWAN_SET_PROVISIONED_CONTEXT_V2)|

For more information about these members, see [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header).

### -field ProvisionedContext

A formatted [**WWAN_SET_PROVISIONED_CONTEXT_V2**](../wwan/ns-wwan-wwan_set_provisioned_context_v2.md) object that represents a provisioned context.

## -remarks

## -see-also

[**WWAN_SET_PROVISIONED_CONTEXT_V2**](../wwan/ns-wwan-wwan_set_provisioned_context_v2.md) 