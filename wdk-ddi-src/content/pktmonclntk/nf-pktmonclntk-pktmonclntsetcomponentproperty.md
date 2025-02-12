---
UID: NF:pktmonclntk.PktMonClntSetComponentProperty
tech.root: 
title: PktMonClntSetComponentProperty
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
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - PktMonClntSetComponentProperty
f1_keywords:
 - PktMonClntSetComponentProperty
 - pktmonclntk/PktMonClntSetComponentProperty
dev_langs:
 - c++
helpviewer_keywords:
 - PktMonClntSetComponentProperty
---

## -description

This function is used to set properties that are meaningful to the component. A component can have multiple properties, and PktMonClntSetComponentProperty should be called once for each one of them. These properties can be used to describe the component in more detail.

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
