---
UID: NS:pktmonclntk._PKTMON_COMPONENT_PROPERTY
tech.root: netvista
title: PKTMON_COMPONENT_PROPERTY
ms.date: 03/14/2025
targetos: Windows
description: The PKTMON_COMPONENT_PROPERTY structure defines various properties for a Packet Monitor component.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_COMPONENT_PROPERTY
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - _PKTMON_COMPONENT_PROPERTY
 - PKTMON_COMPONENT_PROPERTY
f1_keywords:
 - _PKTMON_COMPONENT_PROPERTY
 - pktmonclntk/_PKTMON_COMPONENT_PROPERTY
 - PKTMON_COMPONENT_PROPERTY
 - pktmonclntk/PKTMON_COMPONENT_PROPERTY
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_PROPERTY
---

## -description

The **PKTMON_COMPONENT_PROPERTY** structure defines various properties for a Packet Monitor component.

## -struct-fields

### -field Id

Specifies the identifier for the component property. This field is of type **[PKTMON_COMPONENT_PROPERTY_ID](pktmondefk/ne-pktmondefk-pktmon_co../mponent_property_id.md)**.

### -field IfIndex

Specifies the interface index. Use this field when the property ID is **PktMonCompProp_IfIndex**.

### -field MiniportIfIndex

Specifies the miniport interface index. Use this field when the property ID is **PktMonCompProp_MiniportIfIndex**.

### -field LowerIfIndex

Specifies the lower interface index. Use this field when the property ID is **PktMonCompProp_LowerIfIndex**.

### -field VmsExtIfIndex

Specifies the VMS extension interface index. Use this field when the property ID is **PktMonCompProp_VmsExtIfIndex**.

### -field LowestIfIndex

Specifies the lowest interface index. Use this field when the property ID is **PktMonCompProp_LowestIfIndex**.

### -field NdisMedium

Specifies the NDIS medium type. Use this field when the property ID is **PktMonCompProp_NdisMedium**.

### -field IpIfIndex

Specifies the IP interface index. Use this field when the property ID is **PktMonCompProp_IpIfIndex**.

### -field Vsid

Specifies the virtual subnet ID. Use this field when the property ID is **PktMonCompProp_Vsid**.

### -field Vlan

Specifies the VLAN ID. Use this field when the property ID is **PktMonCompProp_Vlan**.

### -field CompartmentId

Specifies the compartment ID. Use this field when the property ID is **PktMonCompProp_CompartmentId**.

### -field OptDataPath

Specifies the optional data path. Use this field when the property ID is **PktMonCompProp_OptDataPath**.

### -field NdisObject

Specifies the NDIS object type. Use this field when the property ID is **PktMonCompProp_NdisObject**.

### -field EtherType

Specifies the EtherType. Use this field when the property ID is **PktMonCompProp_EtherType**.

### -field IfGuid

Specifies the interface GUID. Use this field when the property ID is **PktMonCompProp_IfGuid**.

### -field MacAddress

Specifies the MAC address. Use this field when the property ID is **PktMonCompProp_PhysAddress**.

### -field VMSwitchName[PKTMON_MAX_PROPERTY_LENGTH_BYTES]

Specifies the name of the VM switch. Use this field when the property ID is **PktMonCompProp_VMSwitchName**.

### -field SockAddr

Specifies the socket address. Use this field when the property ID is **PktMonCompProp_IpAddress**.

## -remarks

## -see-also

- **[PktMon**ClntSetComponentProperty](nf-pktmonclntk-pktmonclntsetcomponentproperty.md)**
- **[PKTMON_COMPONENT_PROPERTY_ID](../pktmondefk/ne-pktmondefk-pktmon_co../mponent_property_id.md)**

