---
UID: NS:pktmonclntnpik._PKTMON_COMPONENT_IN
tech.root: netvista
title: PKTMON_COMPONENT_IN
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_COMPONENT_IN structure contains information about a monitoring component being registered with the Packet Monitor infrastructure.
ai-usage: ai-assisted
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
req.typenames: PKTMON_COMPONENT_IN
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
 - _PKTMON_COMPONENT_IN
 - PKTMON_COMPONENT_IN
f1_keywords:
 - _PKTMON_COMPONENT_IN
 - pktmonclntnpik/_PKTMON_COMPONENT_IN
 - PKTMON_COMPONENT_IN
 - pktmonclntnpik/PKTMON_COMPONENT_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_IN
---

## -description

The **PKTMON_COMPONENT_IN** structure contains information about a monitoring component being registered with the Packet Monitor infrastructure. This structure is passed to the **[PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)** callback during component registration.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header) structure used for versioning and size validation.

### -field CompContext

A pointer to component-specific context data that will be passed back to the component in subsequent callback invocations. This allows components to maintain state information.

### -field Name

A Unicode string containing the name of the component. This name is used for identification and diagnostic purposes.

### -field Description

A Unicode string containing a human-readable description of the component's purpose and functionality.

### -field Type

A **[PKTMON_COMPONENT_TYPE](../pktmondefk/ne-pktmondefk-pktmon_component_type.md)** enumeration value that specifies the type of the component (e.g., network adapter, filter, protocol).

### -field DirTagIn

A Unicode string tag for inbound packet direction. This tag appears in packet logs to identify packets entering the component.

### -field DirTagOut

A Unicode string tag for outbound packet direction. This tag appears in packet logs to identify packets leaving the component.

## -remarks

Components must populate this structure when calling **[PktMonClntComponentRegister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentregister.md)** to register with the monitoring infrastructure.

## -see-also

- [PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)
- [PKTMON_COMPONENT_TYPE](../pktmondefk/ne-pktmondefk-pktmon_component_type.md)
- [PktMonClntComponentRegister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentregister.md)

