---
UID: NC:pktmonclntk.PKTMON_CLNT_UNINITIALIZE
tech.root: netvista
title: PKTMON_CLNT_UNINITIALIZE
ms.date: 02/13/2025
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
 - PKTMON_CLNT_UNINITIALIZE
f1_keywords:
 - PKTMON_CLNT_UNINITIALIZE
 - pktmonclntk/PKTMON_CLNT_UNINITIALIZE
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_UNINITIALIZE
---

## -description

This callback function is invoked when the kernel driver that is acting as a Packet Monitor client is uninitialized.

## -remarks

This function will unregister components that were previously registered by the client and have not been unregistered up to that point. This allows Packet Monitor to free resources that will not be used anymore.

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
