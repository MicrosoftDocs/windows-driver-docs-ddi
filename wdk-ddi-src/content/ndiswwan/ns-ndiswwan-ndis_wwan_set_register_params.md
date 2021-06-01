---
UID: NS:ndiswwan._NDIS_WWAN_SET_REGISTER_PARAMS
tech.root: netvista
title: NDIS_WWAN_SET_REGISTER_PARAMS
ms.date: 06/01/2021
targetos: Windows
description: The NDIS_WWAN_SET_REGISTER_PARAMS structure represents data for OID_WWAN_REGISTER_PARAMS set requests.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndiswwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_WWAN_SET_REGISTER_PARAMS, *PNDIS_WWAN_SET_REGISTER_PARAMS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_SET_REGISTER_PARAMS
 - PNDIS_WWAN_SET_REGISTER_PARAMS
 - NDIS_WWAN_SET_REGISTER_PARAMS
f1_keywords:
 - _NDIS_WWAN_SET_REGISTER_PARAMS
 - ndiswwan/_NDIS_WWAN_SET_REGISTER_PARAMS
 - PNDIS_WWAN_SET_REGISTER_PARAMS
 - ndiswwan/PNDIS_WWAN_SET_REGISTER_PARAMS
 - NDIS_WWAN_SET_REGISTER_PARAMS
 - ndiswwan/NDIS_WWAN_SET_REGISTER_PARAMS
dev_langs:
 - c++
---

## -description

The **NDIS_WWAN_SET_REGISTER_PARAMS** structure represents data for [**OID_WWAN_REGISTER_PARAMS**](/windows-hardware/drivers/network/oid-wwan-register-params) set requests.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_REGISTER_PARAMS** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_REGISTER_PARAMS_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_REGISTER_PARAMS) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header).

### -field SetRegisterParams

A formatted [**WWAN_REGISTRATION_PARAMS_INFO**](../wwan/ns-wwan-wwan_registration_params_info.md) structure that describes the parameters.

## -see-also

[**OID_WWAN_REGISTER_PARAMS**](/windows-hardware/drivers/network/oid-wwan-register-params)

[**NDIS_OBJECT_HEADER**](/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header)

[**WWAN_REGISTRATION_PARAMS_INFO**](../wwan/ns-wwan-wwan_registration_params_info.md)
