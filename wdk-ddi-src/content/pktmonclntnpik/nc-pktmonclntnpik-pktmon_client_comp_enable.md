---
UID: NC:pktmonclntnpik.PKTMON_CLIENT_COMP_ENABLE
tech.root: netvista
title: PKTMON_CLIENT_COMP_ENABLE
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_CLIENT_COMP_ENABLE callback function is invoked by the Packet Monitor client to enable or disable packet monitoring for a specific component.
ai-usage: ai-assisted
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - pktmonclntnpik.h
api_name:
 - PKTMON_CLIENT_COMP_ENABLE
f1_keywords:
 - PKTMON_CLIENT_COMP_ENABLE
 - pktmonclntnpik/PKTMON_CLIENT_COMP_ENABLE
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLIENT_COMP_ENABLE
---

## -description

The **PKTMON_CLIENT_COMP_ENABLE** callback function is invoked by the Packet Monitor client to enable or disable packet monitoring for a specific component. This callback allows components to respond to monitoring state changes by starting or stopping packet capture operations.

## -parameters

### -param Enable

A pointer to a **[PKTMON_CLIENT_COMP_ENABLE_IN](ns-pktmonclntnpik-pktmon_client_comp_enable_in.md)** structure that contains the component context and flags indicating whether flow logging and drop logging should be enabled or disabled.

## -remarks

This callback is part of the **[PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)** structure. Components can use the `FlowEnabled` and `DropEnabled` fields to determine what type of monitoring to perform.

## -see-also

- [PKTMON_CLIENT_COMP_ENABLE_IN](ns-pktmonclntnpik-pktmon_client_comp_enable_in.md)
- [PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)
- [PKTMON_CLIENT_COMP_CLOSE](nc-pktmonclntnpik-pktmon_client_comp_close.md)

