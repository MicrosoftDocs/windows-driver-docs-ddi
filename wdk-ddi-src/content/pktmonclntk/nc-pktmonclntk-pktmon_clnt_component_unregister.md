---
UID: NC:pktmonclntk.PKTMON_CLNT_COMPONENT_UNREGISTER
tech.root: 
title: PKTMON_CLNT_COMPONENT_UNREGISTER
ms.date: 02/10/2025
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
 - PKTMON_CLNT_COMPONENT_UNREGISTER
f1_keywords:
 - PKTMON_CLNT_COMPONENT_UNREGISTER
 - pktmonclntk/PKTMON_CLNT_COMPONENT_UNREGISTER
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_COMPONENT_UNREGISTER
---

## -description

This callback function is invoked when a component is unregistered with Packet Monitor.

## -parameters

### -param CompContext

Pointer to **PKTMON_COMPONENT_CONTEXT** which holds the context for the component. This is the same context used with **PktMonClntComponentRegister**.

## -remarks

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
