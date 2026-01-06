---
UID: NS:pktmonclntnpik._PKTMON_CLIENT_DISPATCH
tech.root: netvista
title: PKTMON_CLIENT_DISPATCH
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_CLIENT_DISPATCH structure contains callback function pointers that the PktMonClnt application provides to handle monitoring events and state changes.
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
req.typenames: PKTMON_CLIENT_DISPATCH
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
 - _PKTMON_CLIENT_DISPATCH
 - PKTMON_CLIENT_DISPATCH
f1_keywords:
 - _PKTMON_CLIENT_DISPATCH
 - pktmonclntnpik/_PKTMON_CLIENT_DISPATCH
 - PKTMON_CLIENT_DISPATCH
 - pktmonclntnpik/PKTMON_CLIENT_DISPATCH
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_CLIENT_DISPATCH
---

## -description

The **PKTMON_CLIENT_DISPATCH** structure contains callback function pointers that the PktMonClnt application provides to handle monitoring events and state changes. This dispatch table defines the client's interface for responding to monitoring control operations.

## -struct-fields

### -field Size

The size of this structure in bytes, used for version validation and compatibility checking.

### -field ClientEnable

A pointer to a **[PKTMON_CLIENT_ENABLE](nc-pktmonclntnpik-pktmon_client_enable.md)** callback function that enables or disables the entire client monitoring infrastructure.

### -field CompEnable

A pointer to a **[PKTMON_CLIENT_COMP_ENABLE](nc-pktmonclntnpik-pktmon_client_comp_enable.md)** callback function that enables or disables monitoring for a specific component.

### -field CompClose

A pointer to a **[PKTMON_CLIENT_COMP_CLOSE](nc-pktmonclntnpik-pktmon_client_comp_close.md)** callback function that notifies the component to clean up when monitoring is disabled.

## -remarks

Clients must initialize this structure with their callback implementations and pass it during client registration to establish the monitoring infrastructure.

## -see-also

- [PKTMON_CLIENT_ENABLE](nc-pktmonclntnpik-pktmon_client_enable.md)
- [PKTMON_CLIENT_COMP_ENABLE](nc-pktmonclntnpik-pktmon_client_comp_enable.md)
- [PKTMON_CLIENT_COMP_CLOSE](nc-pktmonclntnpik-pktmon_client_comp_close.md)

