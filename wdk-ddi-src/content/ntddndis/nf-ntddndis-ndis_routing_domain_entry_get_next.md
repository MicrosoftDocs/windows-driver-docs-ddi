---
UID: NF:ntddndis.NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT
title: NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT macro (ntddndis.h)
description: The NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT macro is used to access the next NDIS_ROUTING_DOMAIN_ENTRY element that follows an NDIS_ROUTING_DOMAIN_ENTRY structure in the array that is specified by an NDIS_ISOLATION_PARAMETERS structure.
tech.root: netvista
ms.assetid: d40e45ee-b7f7-40b4-8152-af1b31c1e971
ms.date: 04/17/2018
f1_keywords:
 - "ntddndis/NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT"
ms.keywords: NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT
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
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddndis.h
api_name: 
- NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT
product:
- Windows
targetos: Windows

---

# NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT macro


## -description

The **NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT** macro is used to access the next [**NDIS_ROUTING_DOMAIN_ENTRY**](ns-ntddndis-_ndis_routing_domain_entry.md) element that follows an **NDIS_ROUTING_DOMAIN_ENTRY** structure in the array that is specified by an [**NDIS_ISOLATION_PARAMETERS**](ns-ntddndis-_ndis_isolation_parameters.md) structure.

## -parameters

### -param _RoutingDomainEntry_

A pointer to an **NDIS_ROUTING_DOMAIN_ENTRY** structure.

## -returns

The **NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT** macro returns a pointer to the next [**NDIS_ROUTING_DOMAIN_ENTRY**](ns-ntddndis-_ndis_routing_domain_entry.md) element in the array. If the *\_RoutingDomainEntry\_* parameter already points to the last element in the array, the macro returns **NULL**.

## -remarks

## -see-also

[**NDIS_ISOLATION_PARAMETERS**](ns-ntddndis-_ndis_isolation_parameters.md)

[**NDIS_ISOLATION_PARAMETERS_GET_FIRST_ROUTING_DOMAIN_ENTRY**](nf-ntddndis-ndis_routing_domain_entry_get_first_isolation_entry.md)

[**NDIS_ROUTING_DOMAIN_ENTRY**](ns-ntddndis-_ndis_routing_domain_entry.md)
