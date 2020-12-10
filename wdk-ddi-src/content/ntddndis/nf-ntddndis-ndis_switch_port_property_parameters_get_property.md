---
UID: NF:ntddndis.NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY
title: NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY macro to access the port property buffer inside an NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure.
tech.root: netvista
ms.date: 04/17/2018
keywords: ["NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY macro"]
ms.keywords: NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY
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
targetos: Windows
f1_keywords:
 - NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY
 - ntddndis/NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY
---

# NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY** macro to access the port property buffer inside an [**NDIS_SWITCH_PORT_PROPERTY_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_parameters.md) structure.

## -parameters

### -param _PortParameters_

A pointer to an **NDIS_SWITCH_PORT_PROPERTY_PARAMETERS** structure.

## -returns

The **NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY** macro returns a pointer to the port property buffer inside an [**NDIS_SWITCH_PORT_PROPERTY_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_parameters.md) structure.

## -remarks

## -see-also

[**NDIS_SWITCH_PORT_PROPERTY_PARAMETERS**](ns-ntddndis-_ndis_switch_port_property_parameters.md)

