---
UID: NE:ntddndis._NDIS_ISOLATION_MODE
title: _NDIS_ISOLATION_MODE (ntddndis.h)
description: The NDIS_ISOLATION_MODE enumeration defines the network isolation modes that can be specified for a VM network adapter.
old-location: netvista\ndis_isolation_mode.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_ISOLATION_MODE enumeration"]
ms.keywords: "*PNDIS_ISOLATION_MODE, NDIS_ISOLATION_MODE, NDIS_ISOLATION_MODE enumeration [Network Drivers Starting with Windows Vista], NdisIsolationModeExternalVirtualSubnet, NdisIsolationModeNativeVirtualSubnet, NdisIsolationModeNone, NdisIsolationModeVlan, _NDIS_ISOLATION_MODE, netvista.ndis_isolation_mode, ntddndis/NDIS_ISOLATION_MODE, ntddndis/NdisIsolationModeExternalVirtualSubnet, ntddndis/NdisIsolationModeNativeVirtualSubnet, ntddndis/NdisIsolationModeNone, ntddndis/NdisIsolationModeVlan"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: NDIS_ISOLATION_MODE, *PNDIS_ISOLATION_MODE
f1_keywords:
 - _NDIS_ISOLATION_MODE
 - ntddndis/_NDIS_ISOLATION_MODE
 - PNDIS_ISOLATION_MODE
 - ntddndis/PNDIS_ISOLATION_MODE
 - NDIS_ISOLATION_MODE
 - ntddndis/NDIS_ISOLATION_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - _NDIS_ISOLATION_MODE
 - PNDIS_ISOLATION_MODE
 - NDIS_ISOLATION_MODE
---

# _NDIS_ISOLATION_MODE enumeration


## -description

The <b>NDIS_ISOLATION_MODE</b> enumeration defines the network isolation modes that can be specified for a VM network adapter.

## -enum-fields

### -field NdisIsolationModeNone

Network isolation is not supported.

### -field NdisIsolationModeNativeVirtualSubnet

Native <b>VirtualSubnetId</b>-based isolation provided by Hyper-V Network Virtualization.

### -field NdisIsolationModeExternalVirtualSubnet

External <b>VirtualSubnetId</b>-based isolation provided by a Hyper-V Extensible Switch extension.

### -field NdisIsolationModeVlan

Virtual local area network (VLAN)-based isolation.

## -remarks

<b>NDIS_ISOLATION_MODE</b> enumeration values are used in the <b>IsolationMode</b> member of the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a> and <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_isolation">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a> structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_isolation">NDIS_SWITCH_PORT_PROPERTY_ISOLATION</a>

