---
UID: NS:pktmonclntnpik._PKTMON_CLIENT_COMP_ENABLE_IN
tech.root: netvista
title: PKTMON_CLIENT_COMP_ENABLE_IN
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_CLIENT_COMP_ENABLE_IN structure contains parameters for enabling or disabling packet monitoring on a specific component.
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
req.typenames: PKTMON_CLIENT_COMP_ENABLE_IN
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
 - _PKTMON_CLIENT_COMP_ENABLE_IN
 - PKTMON_CLIENT_COMP_ENABLE_IN
f1_keywords:
 - _PKTMON_CLIENT_COMP_ENABLE_IN
 - pktmonclntnpik/_PKTMON_CLIENT_COMP_ENABLE_IN
 - PKTMON_CLIENT_COMP_ENABLE_IN
 - pktmonclntnpik/PKTMON_CLIENT_COMP_ENABLE_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_CLIENT_COMP_ENABLE_IN
---

## -description

The **PKTMON_CLIENT_COMP_ENABLE_IN** structure contains parameters for enabling or disabling packet monitoring on a specific component. This structure is passed to the **[PKTMON_CLIENT_COMP_ENABLE](nc-pktmonclntnpik-pktmon_client_comp_enable.md)** callback to control monitoring behavior.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md) structure used for versioning and size validation.

### -field CompContext

A pointer to the component-specific context that was provided during component registration. This context identifies which component is being enabled or disabled.

### -field FlowEnabled

A BOOLEAN value indicating whether packet flow logging should be enabled (TRUE) or disabled (FALSE) for this component.

### -field DropEnabled

A BOOLEAN value indicating whether packet drop logging should be enabled (TRUE) or disabled (FALSE) for this component.

## -remarks

This structure allows selective enabling of flow and drop monitoring, giving components fine-grained control over what packet events they track.

## -see-also

- [PKTMON_CLIENT_COMP_ENABLE](nc-pktmonclntnpik-pktmon_client_comp_enable.md)
- [PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)
- [PKTMON_COMPONENT_IN](ns-pktmonclntnpik-pktmon_component_in.md)

