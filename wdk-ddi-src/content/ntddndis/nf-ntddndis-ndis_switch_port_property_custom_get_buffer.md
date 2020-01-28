---
UID: NF:ntddndis.NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER
title: NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER macro to access the custom port property buffer inside an NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure.
tech.root: netvista
ms.assetid: b59a7108-d5a6-476d-83cf-05de27b3bbae
ms.date: 04/17/2018
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER"
ms.keywords: NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER
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
- NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER
product:
- Windows
targetos: Windows

---

# NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER** macro to access the custom port property buffer inside an [**NDIS_SWITCH_PORT_PROPERTY_CUSTOM**](ns-ntddndis-_ndis_switch_port_property_custom.md) structure.

## -parameters

### -param _PortPropertyCustom_

A pointer to an **NDIS_SWITCH_PORT_PROPERTY_CUSTOM** structure.

## -returns

The **NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER** macro returns a pointer to the custom port property buffer inside an [**NDIS_SWITCH_PORT_PROPERTY_CUSTOM**](ns-ntddndis-_ndis_switch_port_property_custom.md) structure.

## -remarks

## -see-also

[**NDIS_SWITCH_PORT_PROPERTY_CUSTOM**](ns-ntddndis-_ndis_switch_port_property_custom.md)
