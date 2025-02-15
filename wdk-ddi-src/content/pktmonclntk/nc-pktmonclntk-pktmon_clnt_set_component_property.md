---
UID: NC:pktmonclntk.PKTMON_CLNT_SET_COMPONENT_PROPERTY
tech.root: netvista
title: PKTMON_CLNT_SET_COMPONENT_PROPERTY
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
 - PKTMON_CLNT_SET_COMPONENT_PROPERTY
f1_keywords:
 - PKTMON_CLNT_SET_COMPONENT_PROPERTY
 - pktmonclntk/PKTMON_CLNT_SET_COMPONENT_PROPERTY
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_SET_COMPONENT_PROPERTY
---

## -description

This callback function is invoked when properties that are meaningful to the component are set. A component can have multiple properties, and PktMonClntSetComponentProperty should be called once for each one of them. These properties can be used to describe the component in more detail.

## -parameters

### -param CompContext

Pointer to PKTMON_COMPONENT_CONTEXT which holds the context for the component.

### -param CompProperty

Pointer to structure PKTMON_COMPONENT_PROPERTY which describes the property to be set.

## -returns

If the function succeeds, it returns STATUS_SUCCESS. Otherwise, it returns a NTSTATUS error code.

## -remarks

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
