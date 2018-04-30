---
UID: NF:ntddndis.NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY
title: NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY macro
author: windows-driver-content
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY macro to access the extensible switch property buffer inside an NDIS_SWITCH_PROPERTY_PARAMETERS structure.
ms.assetid: a1e79d2b-fd80-4834-a1bb-a7b6cd6fa5f8
ms.author: windowsdriverdev
ms.date: 04/17/2018
ms.topic: macro
ms.keywords: NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY
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
-	NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY
product: Windows
targetos: Windows

---

# NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY** macro to access the extensible switch property buffer inside an [**NDIS_SWITCH_PROPERTY_PARAMETERS**](ns-ntddndis-_ndis_switch_property_parameters.md) structure.

## -parameters

### -param _SwitchParameters_

A pointer to an **NDIS_SWITCH_PROPERTY_PARAMETERS** structure.

## -returns

The **NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY** macro returns a pointer to the extensible switch property buffer inside an [**NDIS_SWITCH_PROPERTY_PARAMETERS**](ns-ntddndis-_ndis_switch_property_parameters.md) structure.

## -remarks

## -see-also

[**NDIS_SWITCH_PROPERTY_PARAMETERS**](ns-ntddndis-_ndis_switch_property_parameters.md)