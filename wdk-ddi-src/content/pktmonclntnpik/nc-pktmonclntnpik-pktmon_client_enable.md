---
UID: NC:pktmonclntnpik.PKTMON_CLIENT_ENABLE
tech.root: netvista
title: PKTMON_CLIENT_ENABLE
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_CLIENT_ENABLE callback function is invoked by the Packet Monitor client to enable or disable the entire client monitoring infrastructure.
ai-usage: ai-assisted
prerelease: true
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
 - PKTMON_CLIENT_ENABLE
f1_keywords:
 - PKTMON_CLIENT_ENABLE
 - pktmonclntnpik/PKTMON_CLIENT_ENABLE
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLIENT_ENABLE
---

## -description

The **PKTMON_CLIENT_ENABLE** callback function is invoked by the Packet Monitor client to enable or disable the entire client monitoring infrastructure. This callback is called at a global level before individual components are enabled or disabled.

## -parameters

### -param Enable

A BOOLEAN value indicating whether to enable (TRUE) or disable (FALSE) packet monitoring for the client. When TRUE, the client should prepare for monitoring operations; when FALSE, the client should clean up monitoring resources.

## -remarks

This callback is part of the **[PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)** structure. It is invoked before component-specific enable callbacks to allow global initialization or cleanup.

## -see-also

- [PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)
- [PKTMON_CLIENT_COMP_ENABLE](nc-pktmonclntnpik-pktmon_client_comp_enable.md)
- [PktMonClntInitialize](../pktmonclntk/nf-pktmonclntk-pktmonclntinitialize.md)

