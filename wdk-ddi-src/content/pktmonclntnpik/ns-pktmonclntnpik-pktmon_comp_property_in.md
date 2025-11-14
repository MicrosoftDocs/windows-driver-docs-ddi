---
UID: NS:pktmonclntnpik._PKTMON_COMP_PROPERTY_IN
tech.root: netvista
title: PKTMON_COMP_PROPERTY_IN
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_COMP_PROPERTY_IN structure contains property information for setting component properties in the Packet Monitor infrastructure.
ai-usage: ai-assisted
prerelease: false
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
req.typenames: PKTMON_COMP_PROPERTY_IN
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
 - _PKTMON_COMP_PROPERTY_IN
 - PKTMON_COMP_PROPERTY_IN
f1_keywords:
 - _PKTMON_COMP_PROPERTY_IN
 - pktmonclntnpik/_PKTMON_COMP_PROPERTY_IN
 - PKTMON_COMP_PROPERTY_IN
 - pktmonclntnpik/PKTMON_COMP_PROPERTY_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_COMP_PROPERTY_IN
---

## -description

The **PKTMON_COMP_PROPERTY_IN** structure contains property information for setting component properties in the Packet Monitor infrastructure. This structure is passed to the **[PKTMON_PROVIDER_SET_COMP_PROPERTY](nc-pktmonclntnpik-pktmon_provider_set_comp_property.md)** callback to configure component behavior.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header) structure used for versioning and size validation.

### -field Id

A **[PKTMON_COMPONENT_PROPERTY_ID](../pktmondefk/ne-pktmondefk-pktmon_component_property_id.md)** enumeration value that identifies which property is being set.

### -field Value

A pointer to the property value data. The format and interpretation of this data depends on the property ID.

### -field Size

The size in bytes of the data pointed to by the `Value` field.

## -remarks

This structure allows dynamic configuration of component properties after registration, enabling runtime adjustments to monitoring behavior.

## -see-also

- [PKTMON_PROVIDER_SET_COMP_PROPERTY](nc-pktmonclntnpik-pktmon_provider_set_comp_property.md)
- [PKTMON_COMPONENT_PROPERTY_ID](../pktmondefk/ne-pktmondefk-pktmon_component_property_id.md)
- [PktMonClntSetComponentProperty](../pktmonclntk/nf-pktmonclntk-pktmonclntsetcomponentproperty.md)

