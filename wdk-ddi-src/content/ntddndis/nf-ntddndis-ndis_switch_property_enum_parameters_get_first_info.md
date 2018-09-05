---
UID: NF:ntddndis.NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
title: NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro
author: windows-driver-content
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro to access the first NDIS_SWITCH_PROPERTY_ENUM_INFO element that is specified by an NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure.
ms.assetid: 545e3463-4ae8-488f-b209-44f8ad12e694
ms.author: windowsdriverdev
ms.date: 04/17/2018
ms.topic: macro
ms.keywords: NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntddndis.h
api_name: 
-	NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO
product:
-	Windows
targetos: Windows

---

# NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO** macro to access the first [**NDIS_SWITCH_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_property_enum_info.md) element that is specified by an [**NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_property_enum_parameters.md) structure.

## -parameters

### -param _SwitchEnumParams_

A pointer to an **NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS** structure.

## -returns

The **NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO** macro returns a pointer to the first [**NDIS_SWITCH_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_property_enum_info.md) element that is specified by an [**NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_property_enum_parameters.md) structure.

## -remarks

## -see-also

[**NDIS_SWITCH_PROPERTY_ENUM_INFO**](ns-ntddndis-_ndis_switch_property_enum_info.md)

[**NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS**](ns-ntddndis-_ndis_switch_property_enum_parameters.md)