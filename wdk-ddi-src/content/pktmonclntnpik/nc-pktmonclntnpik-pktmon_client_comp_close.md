---
UID: NC:pktmonclntnpik.PKTMON_CLIENT_COMP_CLOSE
tech.root: netvista
title: PKTMON_CLIENT_COMP_CLOSE
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_CLIENT_COMP_CLOSE callback function is invoked by the PktMonClnt provider to notify a component that monitoring has been disabled and the component should clean up its resources.
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
 - PKTMON_CLIENT_COMP_CLOSE
f1_keywords:
 - PKTMON_CLIENT_COMP_CLOSE
 - pktmonclntnpik/PKTMON_CLIENT_COMP_CLOSE
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLIENT_COMP_CLOSE
---

## -description

The **PKTMON_CLIENT_COMP_CLOSE** callback function is invoked by the PktMonClnt provider to notify a component that monitoring has been disabled and the component should clean up its resources. This callback is called when a monitoring session ends or when the component is being shut down.

## -parameters

### -param CompContext

A pointer to the component-specific context that was provided during component registration. This context allows the component to identify which instance is being closed and perform appropriate cleanup.

## -remarks

This callback is part of the **[PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)** structure. Components should use this callback to release any resources allocated during monitoring, such as memory buffers or tracking structures.

## -see-also

- [PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)
- [PKTMON_CLIENT_COMP_ENABLE](nc-pktmonclntnpik-pktmon_client_comp_enable.md)
- [PktMonClntComponentUnregister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentunregister.md)

