---
UID: NC:pktmonclntk.PKTMON_CLIENT_COMP_NOTIFY
tech.root: netvista
title: PKTMON_CLIENT_COMP_NOTIFY
ms.date: 03/14/2025
targetos: Windows
description: 
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
 - LibDef
api_location:
 - pktmonclntk.h
api_name:
 - PKTMON_CLIENT_COMP_NOTIFY
f1_keywords:
 - PKTMON_CLIENT_COMP_NOTIFY
 - pktmonclntk/PKTMON_CLIENT_COMP_NOTIFY
dev_langs:
 - c
 - c++
 - c++
helpviewer_keywords:
 - PKTMON_CLIENT_COMP_NOTIFY
---

## -description

Callback function that Packet Monitor calls to notify a component.

## -parameters

### -param CompContext

A pointer to a [PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md) structure containing to context for the component.

## -remarks

Pass a function pointer of this type in the fourth argument of the [PktMonClntInitialize](nf-pktmonclntk-pktmonclntinitialize.md) function. Packet Monitor calls this callback to notify the component.

## -see-also

- [PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)
- [PktMonClntInitialize](nf-pktmonclntk-pktmonclntinitialize.md)
