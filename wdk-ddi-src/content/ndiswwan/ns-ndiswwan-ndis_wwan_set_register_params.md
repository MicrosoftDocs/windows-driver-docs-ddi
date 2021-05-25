---
UID: NS:ndiswwan._NDIS_WWAN_SET_REGISTER_PARAMS
tech.root: 
title: NDIS_WWAN_SET_REGISTER_PARAMS
ms.date: 
targetos: Windows
description: 
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

The **NDIS_WWAN_SET_REGISTER_PARAMS** structure represents data for OID_WWAN_REGISTER_PARAMS set requests.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_REGISTER_PARAMS** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_REGISTER_PARAMS_INFO_REVISION_1 |
| Size | sizeof(NDIS_WWAN_REGISTER_PARAMS_INFO) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field SetRegisterParams

A formatted [**WWAN_SET_REGISTER_PARAMS**](../wwan/ns-wwan-wwan_set_register_params.md) structure that describes the parameters.

## -see-also

[**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md)

[**WWAN_SET_REGISTER_PARAMS**](../wwan/ns-wwan-wwan_set_register_params.md)
