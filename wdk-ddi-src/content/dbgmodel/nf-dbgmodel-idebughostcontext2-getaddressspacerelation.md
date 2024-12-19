---
UID: NF:dbgmodel.IDebugHostContext2.GetAddressSpaceRelation
tech.root: debugger
title: IDebugHostContext2::GetAddressSpaceRelation
ms.date: 12/16/2024
targetos: Windows
description: The GetAddressSpaceRelation method returns the relationship between the virtual memory space of the current context and that of another specified context.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
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
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostContext2::GetAddressSpaceRelation
f1_keywords:
 - IDebugHostContext2::GetAddressSpaceRelation
 - dbgmodel/IDebugHostContext2::GetAddressSpaceRelation
dev_langs:
 - c++
helpviewer_keywords:
 - GetAddressSpaceRelation
---

## -description

The GetAddressSpaceRelation method returns the relationship between the virtual memory space of the current context and that of another specified context. The relationship can indicate how the memory mappings of both contexts interact.

## -parameters

### -param pContext

A pointer to an IDebugHostContext2 instance representing the context to compare against the current context.

### -param pAddressSpaceRelation

A pointer to an [AddressSpaceRelation enum](ne-dbgmodel-addressspacerelation.md) that will receive the result of the relationship between the two contexts' virtual memory spaces.

## -returns

The possible return values are:

- Disjoint: The two contexts share no virtual memory mappings.
- Equal: The two contexts share all virtual memory mappings.
- Overlapping: The two contexts have partially shared memory mappings.
- Subset: The indicated context is a strict subset of the current context.
- Superset: The indicated context is a strict superset of the current context.

## -remarks

## -see-also

[IDebugHostConstant2 interface](nn-dbgmodel-idebughostconstant2.md)