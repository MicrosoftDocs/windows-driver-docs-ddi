---
UID: NS:pktmonclntk._PKTMON_COMPONENT_PROPERTY
tech.root: 
title: PKTMON_COMPONENT_PROPERTY
ms.date: 02/10/2025
targetos: Windows
description: 
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
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_PROPERTY
---

## -description

This struct is used to describe a property of a component in the Packet Monitor.

## -struct-fields

### -field Id

The ID of the property.

### -field IfIndex

Corresponds to PktMonCompProp_IfIndex.

### -field MiniportIfIndex

Corresponds to PktMonCompProp_MiniportIfIndex.

### -field LowerIfIndex

Corresponds to PktMonCompProp_LowerIfIndex.

### -field VmsExtIfIndex

Corresponds to PktMonCompProp_VmsExtIfIndex.

### -field LowestIfIndex

Corresponds to PktMonCompProp_LowestIfIndex.

### -field NdisMedium

Corresponds to PktMonCompProp_NdisMedium.

### -field IpIfIndex

Corresponds to PktMonCompProp_IpIfIndex.

### -field Vsid

Corresponds to PktMonCompProp_Vsid.

### -field Vlan

Corresponds to PktMonCompProp_Vlan.

### -field CompartmentId

Corresponds to PktMonCompProp_CompartmentId.

### -field OptDataPath

Corresponds to PktMonCompProp_OptDataPath.

### -field NdisObject

Corresponds to PktMonCompProp_NdisObject.

### -field EtherType

Corresponds to PktMonCompProp_EtherType.

### -field IfGuid

Corresponds to PktMonCompProp_IfGuid.

### -field MacAddress

Corresponds to PktMonCompProp_PhysAddress.

### -field VMSwitchName[PKTMON_MAX_PROPERTY_LENGTH_BYTES]

Corresponds to PktMonCompProp_VMSwitchName.

### -field SockAddr

Corresponds to PktMonCompProp_IpAddress.

## -remarks

### -see-also

- [PktMonClntSetComponentProperty]()
