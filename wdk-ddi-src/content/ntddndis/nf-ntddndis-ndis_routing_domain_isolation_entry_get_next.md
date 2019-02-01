---
UID: NF:ntddndis.NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT
title: NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT macro (ntddndis.h)
description: Hyper-V extensible switch extensions use the NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT macro to access the next NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY element that follows an NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY structure in the array that is specified by an NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure.
tech.root: netvista
ms.assetid: ad93598f-06c5-41e4-94c3-617c5e07e9ee
ms.date: 04/17/2018
ms.topic: macro
ms.keywords: NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
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
-	NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT
product:
-	Windows
targetos: Windows

---

# NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT macro


## -description

Hyper-V extensible switch extensions use the **NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT** macro to access the next [**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md) element that follows an **NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY** structure in the array that is specified by an [**NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN**](ns-ntddndis-_ndis_switch_port_property_routing_domain.md) structure.

## -parameters

### -param _IsolationInfoEntry_

A pointer to an **NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY** structure.

## -returns

The **NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY_GET_NEXT** macro returns a pointer to the next [**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md) element in the array. If the *\_IsolationInfoEntry\_* parameter already points to the last element in the array, the macro returns **NULL**.

## -remarks

## -see-also

[**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md)

[**NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN**](ns-ntddndis-_ndis_switch_port_property_routing_domain.md)
