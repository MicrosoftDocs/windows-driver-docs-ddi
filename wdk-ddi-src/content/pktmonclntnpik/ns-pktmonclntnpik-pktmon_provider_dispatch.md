---
UID: NS:pktmonclntnpik._PKTMON_PROVIDER_DISPATCH
tech.root: netvista
title: PKTMON_PROVIDER_DISPATCH
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_DISPATCH structure contains callback function pointers that the Packet Monitor provider implements to handle component registration, packet logging, and packet drop operations.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_PROVIDER_DISPATCH
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntnpik.h
api_name:
 - _PKTMON_PROVIDER_DISPATCH
 - PKTMON_PROVIDER_DISPATCH
f1_keywords:
 - _PKTMON_PROVIDER_DISPATCH
 - pktmonclntnpik/_PKTMON_PROVIDER_DISPATCH
 - PKTMON_PROVIDER_DISPATCH
 - pktmonclntnpik/PKTMON_PROVIDER_DISPATCH
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PROVIDER_DISPATCH
---

## -description

The **PKTMON_PROVIDER_DISPATCH** structure contains callback function pointers that the Packet Monitor provider implements to handle component registration, packet logging, and packet drop operations. This dispatch table defines the provider's interface for processing monitoring requests from clients.

## -struct-fields

### -field Size

The size of this structure in bytes, used for version validation and compatibility checking.

### -field ComponentRegister

A pointer to a **[PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)** callback function that registers a new monitoring component.

### -field ComponentUnregister

A pointer to a **[PKTMON_PROVIDER_UNREGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_unregister_component.md)** callback function that unregisters a monitoring component.

### -field SetCompProperty

A pointer to a **[PKTMON_PROVIDER_SET_COMP_PROPERTY](nc-pktmonclntnpik-pktmon_provider_set_comp_property.md)** callback function that sets properties on a registered component.

### -field EdgeAdd

A pointer to a **[PKTMON_PROVIDER_ADD_EDGE](nc-pktmonclntnpik-pktmon_provider_add_edge.md)** callback function that adds a monitoring edge to a component.

### -field PacketLog

A pointer to a **[PKTMON_PROVIDER_PACKET_LOG](nc-pktmonclntnpik-pktmon_provider_packet_log.md)** callback function that logs packet flow events.

### -field PacketDrop

A pointer to a **[PKTMON_PROVIDER_PACKET_DROP](nc-pktmonclntnpik-pktmon_provider_packet_drop.md)** callback function that logs packet drop events.

## -remarks

Providers must initialize this structure with their callback implementations and register it with the Packet Monitor infrastructure to handle monitoring operations.

## -see-also

- [PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)
- [PKTMON_PROVIDER_PACKET_LOG](nc-pktmonclntnpik-pktmon_provider_packet_log.md)
- [PKTMON_PROVIDER_PACKET_DROP](nc-pktmonclntnpik-pktmon_provider_packet_drop.md)

