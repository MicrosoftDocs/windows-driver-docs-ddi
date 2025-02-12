---
UID: NE:pktmondefk._PKTMON_COMPONENT_PROPERTY_ID
tech.root: 
title: PKTMON_COMPONENT_PROPERTY_ID
ms.date: 02/12/2025
targetos: Windows
description: The PKTMON_COMPONENT_PROPERTY_ID enum defines the various properties that can be set for a component in Packet Monitor.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: pktmondefk.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmondefk.h
api_name:
 - _PKTMON_COMPONENT_PROPERTY_ID
 - PKTMON_COMPONENT_PROPERTY_ID
f1_keywords:
 - _PKTMON_COMPONENT_PROPERTY_ID
 - pktmondefk/_PKTMON_COMPONENT_PROPERTY_ID
 - PKTMON_COMPONENT_PROPERTY_ID
 - pktmondefk/PKTMON_COMPONENT_PROPERTY_ID
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_PROPERTY_ID
---

## -description

The **PKTMON_COMPONENT_PROPERTY_ID** enum defines the various properties that can be set for a component in Packet Monitor.

## -enum-fields

### -field PktMonCompProp_IfIndex

Corresponds to the *IfIndex* property.

### -field PktMonCompProp_MiniportIfIndex

Corresponds to the *MiniportIfIndex* property.

### -field PktMonCompProp_LowerIfIndex

Corresponds to the *LowerIfIndex* property.

### -field PktMonCompProp_IfGuid

Corresponds to the *IfGuid* property.

### -field PktMonCompProp_NdisMedium

Corresponds to the *NdisMedium* property.

### -field PktMonCompProp_PhysAddress

Corresponds to the *PhysAddress* property.

### -field PktMonCompProp_EtherType

Corresponds to the *EtherType* property.

### -field PktMonCompProp_OptDataPath

Corresponds to the *OptDataPath* property.

### -field PktMonCompProp_NdisObject

Corresponds to the *NdisObject* property.

### -field PktMonCompProp_VMSwitchName

Corresponds to the *VMSwitchName* property.

### -field PktMonCompProp_VmsExtIfIndex

Corresponds to the *VmsExtIfIndex* property.

### -field PktMonCompProp_LowestIfIndex

Corresponds to the *LowestIfIndex* property.

### -field PktMonCompProp_IpAddress

Corresponds to the *IpAddress* property.

### -field PktMonCompProp_IpIfIndex

Corresponds to the *IpIfIndex* property.

### -field PktMonCompProp_Vsid

Corresponds to the *Vsid* property.

### -field PktMonCompProp_Vlan

Corresponds to the *Vlan* property.

### -field PktMonCompProp_CompartmentId

Corresponds to the *CompartmentId* property.

### -field PktMonCompProp_Max

Must be the last field.

## -remarks

## -see-also

- [PktMonClntSetComponentProperty](../pktmonclntk/nf-pktmonclntk-pktmonclntsetcomponentproperty.md)
