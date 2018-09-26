---
UID: NF:ntddndis.NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY
title: NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY macro
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY macro is used to access the first NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY that is specified by an NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure.
tech.root: netvista
ms.assetid: 7d149940-7927-4a50-af03-6e4feff2ff3e
ms.author: windowsdriverdev
ms.date: 04/17/2018
ms.topic: macro
ms.keywords: NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY
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
-	NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY
product:
-	Windows
targetos: Windows

---

# NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY macro


## -description

The **NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY** macro is used to access the first [**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md) that is specified by an [**NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN**](ns-ntddndis-_ndis_switch_port_property_routing_domain.md) structure.

## -parameters

### -param _RoutingDomainProperty_

A pointer to an **NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN** structure.

## -returns

The **NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_GET_FIRST_ISOLATION_ENTRY** macro returns a pointer to the first [**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md).

## -remarks

## -see-also

[**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md)

[**NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN**](ns-ntddndis-_ndis_switch_port_property_routing_domain.md)
