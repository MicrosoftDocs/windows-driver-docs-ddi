---
UID: NF:ntddndis.NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY
title: NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY macro to access the extensible switch property buffer that is specified by an NDIS_SWITCH_PROPERTY_ENUM_INFO structure.
tech.root: netvista
ms.assetid: 660db1e9-15a3-4002-833c-07bdb191c6b9
ms.date: 04/17/2018
ms.topic: macro
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY"
ms.keywords: NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddndis.h
api_name: 
- NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY
product:
- Windows
targetos: Windows

---

# NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY** macro to access the extensible switch property buffer that is specified by an [**NDIS_SWITCH_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_property_enum_info.md) structure.

## -parameters

### -param _SwitchEnumInfo_

A pointer to an **NDIS_SWITCH_PROPERTY_ENUM_INFO** structure.

## -returns

The **NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY** macro returns a pointer to the extensible switch property buffer.

## -remarks

## -see-also

[**NDIS_SWITCH_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_property_enum_info.md)
