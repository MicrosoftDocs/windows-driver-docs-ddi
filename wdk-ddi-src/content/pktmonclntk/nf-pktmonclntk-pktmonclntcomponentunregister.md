---
UID: NF:pktmonclntk.PktMonClntComponentUnregister
tech.root: netvista
title: PktMonClntComponentUnregister
ms.date: 03/14/2025
targetos: Windows
description: The PktMonClntComponentUnregister function unregisters a component with Packet Monitor.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
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
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - PktMonClntComponentUnregister
f1_keywords:
 - PktMonClntComponentUnregister
 - pktmonclntk/PktMonClntComponentUnregister
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - PktMonClntComponentUnregister
---

## -description

The **PktMonClntComponentUnregister** function unregisters a component with Packet Monitor.

## -parameters

### -param CompContext

Pointer to **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** which holds the context for the component. This is the same context used with **[PktMonClntComponentRegister](nf-pktmonclntk-pktmonclntcomponentregister.md)**.

## -remarks

## -see-also

- **[PktMonClntComponentRegister](nf-pktmonclntk-pktmonclntcomponentregister.md)**
- **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)**
